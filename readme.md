# 已解决
这里可能是因为存在多个gcc版本，且系统默认的gcc版本是低版本的。

使用find / -name gcc命令查找，发现多个目录存在gcc：
/usr/lib/gcc
/usr/local/lib/gcc
/usr/local/bin/gcc
/usr/local/libexec/gcc
/usr/bin/gcc

执行/usr/bin/gcc --version查看版本：
gcc (GCC) 4.4.7-4
/usr/local/bin/gcc --version：
gcc (GCC) 4.8.2
发现多个版本的gcc。

此时：
mv /usr/bin/gcc /usr/bin/gcc4.4.7

ln -s /usr/local/bin/gcc /usr/bin/gcc

mv /usr/bin/g++ /usr/bin/g++4.4.7

ln -s /usr/local/bin/g++ /usr/bin/g++

mv /usr/bin/cc /usr/bin/cc4.4.7

ln -s /usr/local/bin/cc /usr/bin/cc

mv /usr/bin/c++ /usr/bin/c++4.4.7

ln -s /usr/local/bin/c++ /usr/bin/c++
