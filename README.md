# 在subline中使用SpiderMonkey

> [在这里下载SpiderMonkey](https://pan.baidu.com/s/1o6uVEga)
> 下载到桌面（或者别的盘）

- 打开sublime 

- 点击Tools->Build System->New Build System…，

- 在新建的文件中输入以下代码：

```js
{ 
        "cmd": ["js", "$file"], 
}
```

- 保存为SpiderMonkey.sublime-build。

- 重启sublime

- 依次点击Tools->Build System->SpiderMonkey

- 取个名字保存到SpiderMonkey文件夹中（这个文件夹是你下载后解压的文件夹，如果想保存至任意位置请将该路径添加到环境变量Path中）

- 然后按ctrl+B
