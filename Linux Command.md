- 查找非空文件并移动到指定路径
```
find -type -f -size +0 -exec mv {} /dest_addr/ \;
```
- 统计文件夹下文件个数
```
ls -l|grep "^-"|wc -l
```
