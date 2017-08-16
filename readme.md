# I am not familiar with cli, so this is a note about what I has used in my work

## npm

```
# 设置仓库 | 仓库地址是淘宝
npm config set registry http://registry.npm.taobao.org
# 移除仓库地址 | 当然你也可以通过delete命令删除其他项
npm config delete registry
# 查看npm的设置
npm config ls
# 查看npm的所有设置
npm config ls -l
# 运行dev环境脚本,这个主要依赖与你在package.json里面的scripts->dev下面有没有设置
npm run dev
# production参数只会安装devDepdencies
npm install --production
```

## node
```
vim ~/.bashrc
# vim ~/.bash_profile

#配置node的环境变量
export PATH=/home/work/node/v612/bin:$PATH
export NODE_PATH=/home/work/node/v612/lib/node_modules

source ~/.bashrc
```
