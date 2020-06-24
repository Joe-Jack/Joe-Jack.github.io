---
title: powershell常用命令及用法
date: 2020-06-24 20:17
description: 这是网站搭建完成后的第一篇博客。用来测试代码，数学公式。目前发现不能很好地支持数学公式，其暂时没有其他问题。又发现插图片必须使用网址，而不能从本地导入，总而言之，对不会计算机的人不友好。
categories:
- signal
- mathematics
- engineer
- markdown
---

### 1.常用命令及用法

#### 1.打印工作路径（print working directory）

pwd

#### 2.回到home路径

cd ~

注意空格

#### 3.创建目录（make directory）

```CQL
pwd
cd ~
mkdir temp
mkdir temp/stuff      //左斜杠和右斜杠都可以
mkdir -p temp/stuff/things/frank/joa/alex/john

//删除路径
rmdir temp
//确认即可


//创建带空格的文件夹（路径）
mkdir "I have fun"
```

#### 4.更改路径cd

```c
cd temp//进入temp目录
cd stuff/things/frank/joa/alex/john //进入john目录
cd ..// 退出john目录到它的上级目录
pwd //打印工作路径
path
    temp/stuff/things/frank/joa/alex
//退出两级目录到frank目录
cd ../..
//回到home路径
cd ~

```

#### 5.列出目录下的内容

```c
ls
//windows下可以使用 dir -R来完成
```

#### 6.在多个目录中切换

```c
pushd +目录
popd
```

pushd指令作用：记住当前路径，然后到pushd后面的路径中去

popd：回到上次pushd指令记住的目录中去

#### 7.创建空文件

进入temp目录，用`New-Item`创建一个空的cool.txt文本文件

```cli
cd temp
New-Item cool.txt -type file
```

#### 8.复制文件

主要有三种操作

- 将文件复制到另一个同类型文件中去

```c
cp cool.txt next.txt //将cool文件复制并生成新的next文件
```

- 将文件复制到一个目录

```c
//现在temp目录下生成一个something目录
mkdir something
//将cool.txt复制到新目录
cp cool.txt something/
```

- 将一个文件夹复制到另一个新的文件夹

```c
cp -recurse something newplace
//把something文件夹的内容复制到新的和something文件夹同级别的目录newplace中去
```

#### 9.移动文件mv

- 将文件重命名

```c
mv neat.txt neat1.txt
```

- 将文件移动到新的文件夹/或者移动到一个已存在的文件夹

```c
mv newplace oldplace
mv oldplace newplace
```

#### 10.查看文件内容more

```c 
more new.txt // 显示new文件内容
```

#### 11.流文件内容显示

```c
cat test1.txt
```

将test1文件中的所有行一次显示出来

#### 12.删除文件

```c
rm new.txt
//删除文件夹中的文件
rm something/awesome.txt
//删除目录（文件夹）
rmdir something//询问你是否要确认
rm -r newplace//该指令不会询问你要不要确认
```

#### 13.退出命令行

exit