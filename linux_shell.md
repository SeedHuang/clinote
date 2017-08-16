## while case

```
while getopts DBP opt
do
        case $opt in
                D)
                        echo 'Yeah1'
                ;;
                B)
                        echo 'Yeah2'
                ;;
                P)
                        echo 'Yeah3'
                ;;
        esac
done
```

`sh test.sh -DP`

## 变量声明

`$`是使用变量的声明，

```
opt = 1
echo $opt
# 1
```
赋值的时候不用$，直接使用变量名称，如`opt=1`;
在是变量值的时候要$+变量名称，如 `echo $opt`;

## cp

name    | description
--------|-----------
r       |功能上是等价的。不加-r或者－R的时候，只拷贝文件，不拷贝文件夹；加上后则会拷贝文件夹——包括下一级的子文件夹，以及子文件夹中的子文件夹，余此类推。-r的功能是结果反向排列
R       |功能上是等价的。不加-r或者－R的时候，只拷贝文件，不拷贝文件夹；加上后则会拷贝文件夹——包括下一级的子文件夹，以及子文件夹中的子文件夹，余此类推。-R的功能是结果正向排列


## alias

```
while getopts DBP opt
do
	case $opt in
		D)
			echo 'Yeah1'
		;;
		B)
			echo 'Yeah2'
		;;
		P)
			echo 'Yeah3'
		;;
	esac
done
```

打开`vim ~/.bash_profile`

```
# 添加一个alias
alias saytest="/Users/baidu/Desktop/test.sh"
```

授权：`chmod 777 /Users/baidu/Desktop/test.sh`
运行`alias`: `saytest -D`

## `#*`和`##*`

`#*` 从左边开始起删掉满足条件的第一个部分，留下剩余部分

```
var1="Desktop/Users/Application"
echo ${var1##*/}
# Applicataion

echo ${var1#*/}
# Desktopgets
```

`##*` 从右边起保留班组条件的第一个，删除剩余部分


## 压缩和解压

### `tar`

-c: 建立压缩档案
-x：解压
-t：查看内容
-r：向压缩归档文件末尾追加文件
-u：更新原压缩包中的文件

这五个是独立的命令，压缩解压都要用到其中一个，可以和别的命令连用但只能用其中一个。下面的参数是根据需要在压缩或解压档案时可选的。

-z：有gzip属性的
-j：有bz2属性的
-Z：有compress属性的
-v：显示所有过程
-O：将文件解开到标准输出

下面的参数-f是必须的

-f: 使用档案名字，切记，这个参数是最后一个参数，后面只能接档案名。

- `tar -cf all.tar *.jpg`
> 这条命令是将所有.jpg的文件打成一个名为all.tar的包。-c是表示产生新的包，-f指定包的文件名。

- `tar -rf all.tar *.gif`
> 这条命令是将所有.gif的文件增加到all.tar的包里面去。-r是表示增加文件的意思。

- `tar -uf all.tar logo.gif`
> 这条命令是更新原来tar包all.tar中logo.gif文件，-u是表示更新文件的意思。

- `tar -tf all.tar`
> 这条命令是列出all.tar包中所有文件，-t是列出文件的意思

- `tar -xf all.tar`
> 这条命令是解出all.tar包中所有文件，-t是解开的意思

## 压缩

- `tar -cvf jpg.tar *.jpg`
> 将目录里所有jpg文件打包成tar.jpg

- `tar -czf jpg.tar.gz *.jpg`   
> 将目录里所有jpg文件打包成jpg.tar后，并且将其用gzip压缩，生成一个gzip压缩过的包，命名为jpg.tar.gz

- `tar -cjf jpg.tar.bz2 *.jpg`
> 将目录里所有jpg文件打包成jpg.tar后，并且将其用bzip2压缩，生成一个bzip2压缩过的包，命名为jpg.tar.bz2

- `tar -cZf jpg.tar.Z *.jpg`
> 将目录里所有jpg文件打包成jpg.tar后，并且将其用compress压缩，生成一个umcompress压缩过的包，命名为jpg.tar.Z

- `rar a jpg.rar *.jpg`
> rar格式的压缩，需要先下载rar for linux

- `zip jpg.zip *.jpg`
> zip格式的压缩，需要先下载zip for linux

## 解压

- `tar -xvf file.tar`
> 解压 tar包

- `tar -xzvf file.tar.gz`
> 解压tar.gz

- `tar -xjvf file.tar.bz2`
> 解压 tar.bz2

- `tar -xZvf file.tar.Z`
> 解压tar.Z

- `unrar e file.rar`
> 解压rar

- `unzip file.zip`
> 解压zip
