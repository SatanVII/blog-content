---
title: 测试
date: 2024-10-20
category: 藏星
tags:
  - 天文
description: 秋季星空观测笔记。
---

## 织女与牛郎

夏季大三角在十月的天顶缓缓西沉，织女一先落，牛郎随后。

## 仙女座

在无月的夜里，肉眼可以捕捉到 250 万光年外的仙女座星系——一团模糊的光斑，是肉眼可见的最远天体。

```ts
const distance = 2.5e6 // 光年
console.log(`仙女座星系距离：${distance} 光年`)
```


## 前言
本文所介紹內容均在Windows環境下搭建，參考Hexo官方文檔，會詳細介紹搭建過程中所涉及到的命令行。

**それでは、始めましょう！**

## 安裝所需環境
- [Node.js](https://nodejs.org/en)
- [Git](https://git-scm.com/)
請根據官網指示下載安裝至你的電腦

## 安裝Hexo
請打開桌面右鍵出現的Git Bash Here來執行以下所有命令

使用npm命令來進行安裝Hexo
```ts
npm install -g hexo-cli
```


## 開始搭建網站
首先新建一個檔案夾，在所建檔案夾中右鍵打開Git Bash執行
```ts
hexo init blog
```
這一步會生成一個檔案夾

進入生成的檔案夾再次右鍵打開Git Bash（或使用cd命令直接進入），執行npm命令
```
npm install
```
這一步執行後所生成的檔案內容則爲網站的基礎框架

## 安裝主題
進入Hexo官網進入Themes頁面進行尋找，製作人一般會告訴你安裝主題的方法，你也可以通過git clone命令來克隆至你的Theme檔案夾

進入theme檔案夾執行命令
```
git Clone #github項目地址
```
不出意外，你的theme檔案夾中會出現一個新的主題名稱檔案夾，接下來回到根目錄打開你的`_config.yml`文件，找到後方的`Theme：`填寫你所使用的主題名稱

## 啓動服務器
執行命令
```
hexo s
```
執行後會出現` http://localhost:4000/ `將它輸入至你的瀏覽器驗證主題是否顯示正常以及網站搭建成功與否

__如果沒有任何問題的話即可進行下一步連接至GithubPages

## 創建Github庫
名稱爲`你的github用戶名.github.io`其他選項保持默認即可
示例，我的用戶名爲SatanVII,庫名即
```
SatanVII.github.io
```
爲避免問題發生，這一步請不要出錯

## 將庫連接至電腦本地
首先打開Git Bash,輸入命令
```ts
git config --global user.name "你的Github用戶名"
git config --global user.email "你註冊Github的郵箱地址"
```

**接下來獲取你的本機密鑰
Windows打開檔案`C:/Users/name/.ssh`打開`id_rsa.pub`文件複製當中的密鑰

### 將密鑰儲存至Github
打開Github點擊頭像-Settings,在設定中找到SSH and GPG keys,點擊New SSH key新建
[![HiaKQWJ.md.png](https://iili.io/HiaKQWJ.md.png)](https://freeimage.host/i/HiaKQWJ)
## 測試密鑰連接是否成功
在git bash中輸入命令
```
ssh -T git@github.com
```

如出現
```ts
The authenticity of host 'github.com (207.97.227.239)' can't be established.  
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.  
Are you sure you want to continue connecting (yes/no)?  
# yes 
Hi username! You've successfully authenticated, but GitHub does not  
provide shell access.
```
則成功

## 將Hexo部署至GithubPages
- 安裝部署插件
```
npm install hexo-deployer-git --save
```

- 修改`_config.yml`中`deploy`配置
打開根目錄`_config.yml`文件在最後方添加以下內容
```
deploy:  
  type: git  
  repo:  https://github.com/name/name.github.io 
  barnch: main
  ```
repo下填寫你所出創建的庫的地址  

- 執行命令
```
hexo clean && hexo deploy
```

接下來查看網址`<GitHub 用戶名>.github.io`來檢測你的網站是否運作正常


至此搭建大致完成，後續完善還請自行翻看官方文檔

**じゃね~**
