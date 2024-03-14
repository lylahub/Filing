# Hey! I'm Filing Here

In this lab, I successfully implemented a 1 MiB ext2 file system with 2 directories, 1 regular file, and 1 symbolic link given the ext2 structures and some initial skeleton code which creates a file called cs111-base.img in the current working directory.

## Building

```shell
make
```

## Running

```shell
mkdir mnt

./ext2-create
sudo mount -o loop cs111-base.img mnt
cd mnt
ls -ain
```

Result:
```shell
total 7
     2 drwxr-xr-x 3    0    0 1024 Mar 13 22:16 .
942330 drwxrwxr-x 3 1000 1000 4096 Mar 13 22:16 ..
    13 lrw-r--r-- 1 1000 1000   11 Mar 13 22:16 hello -> hello-world
    12 -rw-r--r-- 1 1000 1000   12 Mar 13 22:16 hello-world
    11 drwxr-xr-x 2    0    0 1024 Mar 13 22:16 lost+found
```


## Cleaning up

```shell
cd ..
sudo umount mnt
rmdir mnt
make clean
```
