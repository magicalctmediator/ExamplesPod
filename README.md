# ExamplesPod

1.Cocoapods注册Trunk

>$ pod trunk register [Your-Email] '[Your-Name]' --description='[Your-Desc]'

> >[Your-Email]: 任意邮件，推荐使用github上的Email
> >[Your-Name]: 推荐使用github上使用的Name
> >[Your-Desc]: 一个简单的描述

>$ pod trunk register dreamingclear@163.com 'qian' --description='mengxiang Mac Pro 13'

注册完成后查看信息
>$ pod trunk me  

2. 部署一个开源的pod

>$ git clone git@github.com:magicalctmediator/ExamplePod.git

完成之后进入到所在目录
>$ cd ../ExamplePod

创建.podspec
>$ pod spec create [NAME]  

[NAME]: podspec 名称，一般与你在git上创建的repository相同 如：

>$ pod spec create ExamplePod

一般会先创建一个文件夹，用于放置{.h/.m/.swift  Assets}等
>$ mkdir Sources
将你所需的文件拷贝至文件夹，如下就是这个pod的


3
添加所有文件
> $ git add . 

提交
>$ git commit -m "Initial ExamplePod"

push到你的远程仓库
>$ git push

接下来就是需要使用到的一个Tag，这个在你的.podspec中需要配置
>$ git tag -m "Initial Tag" 0.0.1

将tag添加至你的远程仓库
>$ git push --tags


4. 修改.podspec



5.通过手动方式检验一下你的.podspec是否正确
进入到.podspec所在目录
>$ pod spec lint
如果出现错误，需要修改到提示无误后方可执行下一步

6.提交公有library

>$ pod trunk push [NAME].podspec

7.是否成功 先更新一下repo

>$ pod repo update

查找一下你提交的pod

>$ pod search 'ExamplePod'


tips: 如果你在pod search无法找到你的pod，可以参照以下步骤：
执行 pod repo update 后重新pod search
或者：pod setup 然后删除 rm ~/Library/Caches/CocoaPods/search_index.json 再重新pod search。
