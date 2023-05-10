#  Git

在Mac上  配置git出现无法拉取的情况，目前个人已知原因是由于代理软件原因，禁止了github的 ssh连接服务，需要修改.ssh/config

```
Host github.com
  HostName ssh.github.com
  User git
  Port 443

```

MacOS 查看.ssh文件目录命令open ./.ssh

对代码进行覆盖之后，首先进入 仓库目录进行文件对比

```jsx
git add .
```

对比之前的文件

```jsx
git status
```

添加修改 描述

```jsx
git commit -m "描述"
```

最后 

```jsx
git push
```

站长工具对 github进行ping测试，找到延迟相对较低的响应ip，之后修改Mac上的 host文件(进入以下目录)

```jsx
/private/etc/hosts
```

![Untitled](%EF%A3%BF%20Git%202d46a1bedee34c3991ecf526d77a114a/Untitled.png)

修改内容为(蓝色部分自行测试更换)

```jsx
20.205.243.166  github.com
20.205.243.160  ssh.git@github.com
```

## 远端仓库发生变更 ，本地仓库与远端仓库进行同步

1.查看远端仓库

```jsx
git remote -v
```

2.从远端仓库获取最新版

```jsx
git fetch origin main
```

3.远端代码与本地合

```jsx
git merge origin
```