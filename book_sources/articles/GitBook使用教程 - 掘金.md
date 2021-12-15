# GitBook使用教程 - 掘金

> 你好，我是悅創。首發博客：https://www.aiyc.top/1947.html 公眾號：AI悅創 1. 環境搭建 1.1 安裝 Nodejs 大佬級別直接看下面這句話，就沒啥問題： 這個安裝

你好，我是悅創。

首發博客：[www.aiyc.top/1947.html](https://link.juejin.cn/?target=https%3A%2F%2Fwww.aiyc.top%2F1947.html "https://www.aiyc.top/1947.html")

公眾號：AI悅創

> 詳細的記錄了一步步搭建自己的電子文檔筆記

# 1. 環境搭建

1.1 安裝 Nodejs
-------------

大佬級別直接看下面這句話，就沒啥問題：

這個安裝很簡單，只需要下載，然後一路 next 即可。下載鏈接：[nodejs.org/en/](https://link.juejin.cn/?target=https%3A%2F%2Fnodejs.org%2Fen%2F "https://nodejs.org/en/")

小白繼續看看下來：

用於所有主流平台的官方軟件包，可訪問 [nodejs.cn/download/](https://link.juejin.cn/?target=http%3A%2F%2Fnodejs.cn%2Fdownload%2F "http://nodejs.cn/download/")

安裝 Node.js 的其中一種非常便捷的方式是通過軟件包管理器。對於這種情況，每種操作系統都有其自身的軟件包管理器。

在 macOS 上，[Homebrew](https://link.juejin.cn/?target=https%3A%2F%2Fbrew.sh%2F "https://brew.sh/") 是業界的標準，在安裝之後可以非常輕鬆地安裝 Node.js（通過在 CLI 中運行以下命令）：
```
    brew install node
```

其他適用於 Linux 和 Windows 的軟件包管理器列出在 [nodejs.org/en/download…](https://link.juejin.cn/?target=https%3A%2F%2Fnodejs.org%2Fen%2Fdownload%2Fpackage-manager%2F "https://nodejs.org/en/download/package-manager/")。

nvm 是一種流行的運行 Node.js 的方式。例如，它可以輕鬆地切換 Node.js 版本，也可以安裝新版本用以嘗試並且當出現問題時輕鬆地回滾。

這對於使用舊版本的 Node.js 來測試代碼非常有用。

詳見 [github.com/creationix/…](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fcreationix%2Fnvm "https://github.com/creationix/nvm")。

建議，如果剛入門並且還沒有用過 Homebrew，則使用官方的安裝程序，否則，Homebrew 是更好的解決方案。

無論如何，當安裝 Node.js 之後，就可以在命令行中訪問 node 可執行程序。

1.2 gitbook-cli 腳手架安裝
---------------------

1.  命令安裝
```
    npm install -g gitbook-cli
```

2.  版本驗證
```
    # gitbook -V
    CLI version: 2.3.2
    GitBook version: 3.2.3
```

3.  編譯器的選擇:推薦下面兩個
    
4.  vscode
    
5.  Typora
    
6.  sublimeText3




# 2. 創建目錄，初始化

```
    mkdir gitbook-imsdk   // 創建項目目錄
    cd gitbook-imsdk
    gitbook init  // 初始化目錄
```

**PS: 如果初始化報錯的話：**
```
    TypeError [ERR_INVALID_ARG_TYPE]: The "data" argument must be of type string or an instance of Buffer, TypedArray, or DataView. Received an instance of Promise
```

經排查，node 版本過高，降低一下 nodejs 版本即可。但是需要重新安裝？ ——可以重新安裝，但是不划算也沒有技術的體現。使用 nvm，至於什麼是 nvm 點擊此文章閱讀：[NVM 常用命令](https://link.juejin.cn/?target=https%3A%2F%2Fwww.aiyc.top%2F1946.html "https://www.aiyc.top/1946.html")
```
    nvm list
    nvm use vxxxx
    然後從新進入 cd gitbook-imsdk
    gitbook init
```

PS:
```
    # nvm list
    
      * 14.18.0 (Currently using 64-bit executable)
        10.12.0
    
    # nvm use v10.12.0
    Now using node v10.12.0 (64-bit)
```

初始化完成，默認生成兩個文件：`SUMMARY.md`，`README.md`

![在這裡插入圖片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/afe4a89159294698b0664c668fb5f7ea~tplv-k3u1fbpfcp-watermark.awebp)

# 3. 詳細說明

3.1 編寫 README and SUMMARY
-------------------------

此文件為章節目錄設置文件，如果我們想為我們的創作添加章節目錄，我們可以利用 Sumary.md 文件進行章節目錄劃分，此文件的書寫格式也比較簡單，例如：

### 3.1.1 README.md

這個文件相對於是一本 Gitbook 的簡介，比如我們這本書的 `README.md` :
```
    # Gitbook 使用入門
    
    
    > GitBook 是一個基於 Node.js 的命令行工具，可使用 Github/Git 和 Markdown 來製作精美的電子書。
    
    本書將簡單介紹如何安裝、編寫、生成、發布一本在線圖書。
```

### 3.1.2 SUMMARY.md

這個文件相對於是一本書的目錄結構。比如我們這本書的 `SUMMARY.md` :
```
    # Summary
    
    * [Introduction](README.md)
    * [基本安裝](howtouse/README.md)
       * [Node.js安裝](howtouse/nodejsinstall.md)
       * [Gitbook安裝](howtouse/gitbookinstall.md)
       * [Gitbook命令行速覽](howtouse/gitbookcli.md)
    * [圖書項目結構](book/README.md)
       * [README.md 與 SUMMARY編寫](book/file.md)
       * [目錄初始化](book/prjinit.md)
    * [圖書輸出](output/README.md)
       * [輸出為靜態網站](output/outfile.md)
       * [輸出PDF](output/pdfandebook.md)
    * [發布](publish/README.md)
       * [發佈到Github Pages](publish/gitpages.md)
    * [結束](end/README.md)
```

`SUMMARY.md` 基本上是列表加鏈接的語法。鏈接中可以使用目錄，也可以使用。

3.2 本地預覽
--------

### 3.2.1 gitbook init

在預覽之前，還需要做一步操作。

當 README.md、SUMMARY.md 創建完畢之後，我們可以使用 Gitbook 的命令行工具將這個目目錄結構生成相應地目錄及文件
```
    $ gitbook init # 命令得到的輸出省略
    
    $ ls
    README.md    SUMMARY.md    book    end    howtouse    output    publish
    
    $tree
    .
    ├── README.md
    ├── SUMMARY.md
    ├── book
    │   ├── README.md
    │   ├── file.md
    │   └── prjinit.md
    ├── howtouse
    │   ├── Nodejsinstall.md
    │   ├── README.md
    │   ├── gitbookcli.md
    │   └── gitbookinstall.md
    ├── output
    │   ├── README.md
    │   ├── outfile.md
    │   └── pdfandebook.md
    └── publish
        ├── README.md
        └── gitpages.md
```

我們可以看到，gitbook 給我們生成了與 `SUMMARY.md` 所對應的目錄及文件。

每個目錄中，都有一個 `README.md` 文件，用於描述這一章的說明。

### 3.2.2 gitbook serve

接下來，我們使用
```
    gitbook serve ./{book_name}
```

我的操作，啟動服務，進行預覽：
```
    gitbook serve
```

啟動完之後，瀏覽器輸入：`http://localhost:4000`

**注意：**

可以事先創建好文章目錄，通過執行 gitbook init 自動生成對應的文件，然後在 gitbook serve。

3.3 圖書輸出
--------

目前為止，Gitbook 支持如下輸出：

*   靜態 HTML，可以看作一個靜態網站
*   PDF 格式
*   eBook格式
*   單個 HTML 文件
*   JSON 格式

我們這裡著重說下如何輸出靜態的 HTML 和 PDF 文件。

### 3.3.1 輸出為靜態網站

你有兩種方式輸出一個靜態的網站：

#### 1\. 本地預覽是自動生成

當你編輯好 gitbook 文檔之後，你可以使用 gitbook 的命令來進行本地預覽。
```
    gitbook serve ./{book_name}
```

gitbook 會啟動一個 4000 端口用於預覽。

比如，通過 `gitbook serve` 來預覽本文檔：
```
    clela@AIYC D:\gitee_all\quicksand_suanfa
    # gitbook serve
    Live reload server started on port: 35729
    Press CTRL+C to quit ...
    
    info: 7 plugins are installed
    info: loading plugin "livereload"... OK
    info: loading plugin "highlight"... OK
    info: loading plugin "search"... OK
    info: loading plugin "lunr"... OK
    info: loading plugin "sharing"... OK
    info: loading plugin "fontsettings"... OK
    info: loading plugin "theme-default"... OK
    info: found 14 pages
    info: found 13 asset files
    info: >> generation finished with success in 1.0s !
    
    Starting server ...
    Serving book on http://localhost:4000
```

你可以你的瀏覽器中打開這個網址： [http://localhost:4000](https://link.juejin.cn/?target=http%3A%2F%2Flocalhost%3A4000 "http://localhost:4000")

![在這裡插入圖片描述](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d61e902a5a454dc69604e194f0669e9c~tplv-k3u1fbpfcp-watermark.awebp)

你會發現，在你編輯的 gitbook項目的目錄中會多一個 `_book` 目錄，而這個目錄中就是生成的本地預覽的靜態網站內容。

#### 2\. 使用 gitbook build 參數

與直接預覽生成的靜態網站不一樣的時，使用這個命令，你可以將內容輸出到你想要的目錄。

> Ps：`gitbook build ./{book_name} --output=./{outputFolde}` `gitbook build [當前路徑] [輸出路徑]` `gitbook build ./ doc # 默認打包輸出到當前路徑下面的 doc 文件夾中`
```
    $ gitbook build --output=/tmp/gitbook
    Starting build ...
    Successfuly built !
    $ ls /tmp/gitbook/
    howtouse          search_index.json
    book              imgs              output
    gitbook           index.html        publish
```

**注意：**

打包成功之後，默認輸出的文件放在 `_book` 文件夾裡面，編譯之後的入口： `index.html`

**無論哪種方式，你都可以將這個靜態網站打包，發佈到你想要發布的服務器上，或者直接將這個打包文件給閱讀者。 **

### 3.3.2 輸出 PDF

輸出為 PDF 文件，需要先安裝 `gitbook pdf`
```
    npm install gitbook-pdf -g
```

> 一般來說，不推薦安裝全局環境，安裝局部環境會比較好。

> 如果在安裝 gitbook-pdf 時，覺得下載 phantomjs 包太慢的話，你可以到 phantomjs 的官方網站上去下載。 [phantomjs.org/](https://link.juejin.cn/?target=http%3A%2F%2Fphantomjs.org%2F "http://phantomjs.org/") 這個包的安裝方式，參考其官網的說明文檔。

**當然，上面的方法，我試了，以失敗告終。所以我換了一種方法。 **

Windows下使用 gitbook 生成PDF文件：[www.aiyc.top/1969.html](https://link.juejin.cn/?target=https%3A%2F%2Fwww.aiyc.top%2F1969.html "https://www.aiyc.top/1969.html")

然後，用下面的命令就可以生成 PDF 文件了。
```
    gitbook pdf {book_name}
```

如果，你已經在編寫的 gitbook 當前目錄，也可以使用相對路徑。
```
    gitbook pdf .
```

然後，你就會發現，你的目錄中多了一個名為 `book.pdf` 的文件。

3.4 查看幫助
--------
```
    clela@AIYC D:\gitee_all\quicksand_suanfa
    # gitbook -h
    
      Usage: gitbook [options] [command]
    
    
      Options:
    
        -v, --gitbook [version]  specify GitBook version to use
        -d, --debug              enable verbose error
        -V, --version            Display running versions of gitbook and gitbook-cli
        -h, --help               output usage information
    
    
      Commands:
    
        ls                        List versions installed locally
        current                   Display currently activated version
        ls-remote                 List remote versions available for install
        fetch [version]           Download and install a <version>
        alias [folder] [version]  Set an alias named <version> pointing to <folder>
        uninstall [version]       Uninstall a version
        update [tag]              Update to the latest version of GitBook
        help                      List commands for GitBook
        *                         run a command with a specific gitbook version
```

3.5 發布
------

可以使用 Github Pages 服務將我們寫的 gitbook 發佈到互聯網上，前提是你已經了解了 Git、Github 及 Github Pages 的使用。

### 3.5.1 發佈到 Github Pages

#### 1\. 將靜態網站直接發佈到 Github Pages

可以將編寫好的 `.md` 文件通過 Gitbook 處理成靜態網站，然後發佈到[Github Pages](https://link.juejin.cn/?target=https%3A%2F%2Fpages.github.com%2F "https://pages.github.com/") 上。

這個參考這個：\[[www.yuque.com/docs/share/…](https://link.juejin.cn/?target=https%3A%2F%2Fwww.yuque.com%2Fdocs%2Fshare%2F9afacf4e-005e-4c5e-8373-a81af2940a68%3F%23 "https://www.yuque.com/docs/share/9afacf4e-005e-4c5e-8373-a81af2940a68?#") 《利用 GitHub 從零開始搭建一個博客》\]([www.yuque.com/docs/share/…](https://link.juejin.cn/?target=https%3A%2F%2Fwww.yuque.com%2Fdocs%2Fshare%2F9afacf4e-005e-4c5e-8373-a81af2940a68%3F%23 "https://www.yuque.com/docs/share/9afacf4e-005e-4c5e-8373-a81af2940a68?#") 《利用 GitHub 從零開始搭建一個博客》)

### 3.5.2 使用項目的 Pages 服務

除了上面的直接發布靜態文件到 Github Pages 的方法以外，還可以使用一個單獨的項目的 Github Pages 功能。

#### 1\. 創建倉庫與分支

1.  登陸到 Github，創建一個新的倉庫，名稱我們就命名為 `book` ，這樣我就得到一個 `book` 倉庫。 （創建的時候小白推薦選上 `README.md` 初始化）
2.  克隆倉庫到本地： `git clone git@github.com:/USER_NAME/book.git`
3.  創建一個新分支： `git checkout -b gh-pages`，注意，分支名必須為 `gh-pages` 。
4.  將分支 push 到倉庫： `git push -u origin gh-pages`。
5.  切換到主分支：`git checkout main`。

經過這一步處理，我們已經創建了 `gh-pages` 分支了，有了這個分支，Github會自動為你分配一個網址。

> [USERNAME.github.io/book](https://link.juejin.cn/?target=http%3A%2F%2FUSERNAME.github.io%2Fbook "http://USERNAME.github.io/book")

**同步靜態網站代碼到分支：**

下面我們就可以將 build 好的靜態網站代碼同步到 `gh-pages` 分支中去了。

把 build 成功的文件複製到 book 本地的 book 文件夾中。

1.  切換 git 分支
```
    git checkout gh-pages # 需要按上面的步驟操作，上面的步驟操作後也會自動切換分支
```

我的實際操作：
```
    aiyc@aiyc:/mnt/d/Github_pages/book$ git checkout gh-pages
    Switched to branch 'gh-pages'
    Your branch is up to date with 'origin/gh-pages'.
```

接下來，輸入下面的一系列命令：
```
    git add .
    git commit -m "first commit"
    git push
```

然後，等十來分鐘後，你就可以訪問到你的在線圖書了。以後，只要你每次修改之後，將生成靜態網站 Copy 到 `book` 目錄，然後運行上面三條命令一下就 OK 了。

後面會更新插件的用法，敬請期待！

> AI悅創·V：Jiabcdefh

參考:
- [Source](https://juejin.cn/post/7017663651066839071)