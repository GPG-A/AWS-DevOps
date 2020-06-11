## 一、Docker Devicemapper存储介绍
DeviceMapper自Linux 2.6被引入。它在内核中支持逻辑卷管理的通用设备映射机制，它为实现用于存储资源管理的块设备驱动提供了一个高度模块化的内核和架构，包含三个重要的对象概念，MapperDevice，Mapping Table, Target device。
```markdown
- Mapped Device 是一个逻辑抽象，可以理解成为内核向外提供的逻辑设备，它通过Mapping Table描述的映射关系和Target Device建立映射。Target device表示的是Mapped Device所映射的物理空间段，对Mapped Device所表示逻辑设备来收，就是该逻辑设备映射到的一个物理设备。
- Mapping Table里有 Mapped Device 逻辑的起始地址、范围、和表示在 Target Device 所在物理设备的地址偏移量以及Target 类型等信息（注：这些地址和偏移量都是以磁盘的扇区为单位的，即 512 个字节大小，所以，当你看到128的时候，其实表示的是128*512=64K）。
- DeviceMapper 中的逻辑设备Mapped Device不但可以映射一个或多个物理设备Target Device，还可以映射另一个Mapped Device，于是，就是构成了一个迭代或递归的情况，就像文件系统中的目录里除了文件还可以有目录，理论上可以无限嵌套下去。
- devicemapper驱动将每一个Docker镜像和容器存储在它自身的具有精简置备(thin-provisioned)、写时拷贝(copy-on-write)和快照功能(snapshotting)的虚拟设备上。由于Device Mapper技术是在块(block)层面而非文件层面，所以Docker Engine的devicemapper存储驱动使用的是块设备来存储数据而非文件系统。
```
## 二、LVM介绍
LVM [ Logical Volume Manager ] 是一种可用在Linux内核的逻辑分卷管理器；可用于管理磁盘驱动器或其他类似的大容量存储设备。
```markdown
LVM利用Linux内核的功能来实现存储系统的虚拟化（系统分区独立于底层硬件）。 通过LVM，你可以实现存储空间的抽象化并在上面建立虚拟分区（virtual partitions），可以更简便地扩大和缩小分区，可以增删分区时无需担心某个硬盘上没有足够的连续空间，避免为正在使用的磁盘重新分区的麻烦、为调整分区而不得不移动其他分区的不便。

### LVM的基本组成部分如下：
- 物理卷 (PV)
一个可供存储LVM的块设备. 例如: 一块硬盘, 一个MBR或GPT分区, 一个回环文件, 一个被内核映射的设备 (例如 dm-crypt).它包含一个特殊的LVM头。
- 卷组 (VG)
物理卷的一个组，作为存放逻辑卷的容器。 PEs are allocated from a VG for a LV.
- 逻辑卷 (LV)
"虚拟/逻辑卷"存放在一个卷组中并由物理块组成。是一个类似于物理设备的块设备，例如，你可以直接在它上面创建一个文件系统文件系统。
- 物理块 (PE)
一个卷组中最小的连续区域(默认为4 MiB)，多个物理块将被分配给一个逻辑卷。你可以把它看成物理卷的一部分，这部分可以被分配给一个逻辑卷。

### LVM的优点
比起普通的硬盘分区管理方式，LVM更富于灵活性：
* 将多块硬盘看作一块大硬盘
* 使用逻辑卷（LV），可以创建跨越众多硬盘空间的分区。
* 可以创建小的逻辑卷（LV），在空间不足时再动态调整它的大小。
* 在调整逻辑卷（LV）大小时可以不用考虑逻辑卷在硬盘上的位置，不用担心没有可用的连续空间。
* 可以在线（online）对逻辑卷（LV）和卷组（VG）进行创建、删除、调整大小等操作。不过LVM上的文件系统也需要重新调整大小，好在某些文件系统（例如ext4）也支持在线操作。
* 无需重新启动服务，就可以将服务中用到的逻辑卷（LV）在线（online）/动态（live）迁移至别的硬盘上。
* 允许创建快照，可以保存文件系统的备份，同时使服务的下线时间（downtime）降低到最小。
* 支持各种设备映射目标（device-mapper targets），包括透明文件系统加密和缓存常用数据（caching of frequently used data）。这将允许你创建一个包含一个或多个磁盘、并用LUKS加密的系统，使用LVM on top 可轻松地管理和调这些整独立的加密卷 （例如. `/`, `/home`, `/backup`等) 并免去开机时多次输入密钥的麻烦。
```
## 三、Linxu命令的使用
- dnf：新一代的RPM软件包管理器
- scp
- hostnamectl
- systemctl
- sysctl

## 四、Docker加速镜像配置
```shell
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://2ktcsipk.mirror.aliyuncs.com"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
```

