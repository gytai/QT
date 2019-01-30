# QT 在Mac编译以及引用Poco

#### 1. 获取最新源码（我编译时候是1.9.0）

```
git clone -b master https://github.com/pocoproject/poco.git
```

#### 2. 编译
> 官方建议使用Cmake 编译。所以我用的也是的Cmake。建议Cmake 版本是3.0或者以后。进入Poco源码根目录，执行以下命令。

```
$ mkdir cmake-build
$ cd cmake-build
$ cmake .. && cmake --build .
```

> 安装Poco到 /usr/local

```
$ sudo cmake --install .
```

> 如此便编译安装好了。头文件目录：/usr/local/include。动态库目录：/usr/local/lib。

> QT 下引用POCO库实例(动态库引用debug版本和Release版本)：

```
INCLUDEPATH += /usr/local/include
LIBS += -L"/usr/local/lib" -lPocoFoundationd -lPocoJSONd -lPocoNetd -lPocoUtild -lPocoXMLd
LIBS += -L"/usr/local/lib" -lPocoFoundation -lPocoJSON -lPocoNet -lPocoUtil -lPocoXML
```
