# Otake-lab.site

## ファイル構成
[jekyll](http://jekyllrb-ja.github.io/)という静的サイトジェネレータを使用しています．markdownで記事がかけます．便利．  

```
   ./
    ├── _config.yml             # * jekyll用のconfigファイル
    ├── _includes               # Layoutでincludeするファイル（普段はさわらない）
    |   ├── footer.html         
    |   └── header.html
    ├── _layouts                # Layoutを定義するファイル（普段はさわらない）
    |   ├── default.html
    |   └── post.html
    ├── _posts                  # * 投稿（markdownで書きます）
    |   ├── 2007-10-29-this-is-posts.md
    |   └── 2009-04-26-hahaha.md
    ├── _sass                   # sassを突っ込んどくところ（普段はさわらない）
    |   ├── _base.scss
    |   └── _layout.scss
    ├── _site                   # 出力用フォルダ（この中身は自動生成なので保存しません！）
    ├── member.html             # * メンバー一覧
    ├── contact.html            # * 連絡先
    ├── news.html               # * ニュース
    └── index.html              # * トップページ
    
```

## Newsの更新方法


1. リポジトリをクローン．
    ```bash
    git clone https://github.com/otake-lab/otake-lab.github.io
    cd otake-lab.github.io
    ``` 

2. `_posts`以下に`YYYY-MM-DD-title.md`でファイルを作ります．

    ```bash
    cd _posts
    # Ex. 2020-06-23-test.md
    vim 2020-06-23-test.md
    ```

3. 作った`YYYY-MM-DD-title.md`をテキストエディタで編集します．

    ```
    ---
    layout: post
    title:  "新入生歓迎会を行いました"
    ---

    本日，新入生歓迎会を行いました．
    今年度は新たに〇〇名の仲間が加わります！

    ```

4. 作ったファイルをcommit&pushします．

    ```bash
    git add .
    git commit -m "Add YYYY-MM-DD-title.md"
    git push
    ```

5. GitHub上でpullrequestを出します．（4までできたら担当者に連絡してください．）

6. masterにmergeされれば公開されます．**自動でNews，Index等が更新されます**．

## Deployment

ローカルでプレビュー等したい人向け，News以外のページを更新する場合もこちら．

- WSLを有効にする  
    https://docs.microsoft.com/ja-jp/windows/wsl/install-win10

- WSLのbashで環境構築（以下すべてWSL上で操作）
    ```bash
    sudo apt-get update -y && sudo apt-get upgrade -y

    sudo apt-add-repository ppa:brightbox/ruby-ng
    sudo apt-get update
    sudo apt-get install ruby2.5 ruby2.5-dev build-essential dh-autoreconf
    ```

    ```bash
    gem update
    ```

    ```bash
    # jekyllをインストール
    gem install jekyll bundler
    ```

- リポジトリをクローン

    ```bash 
    git clone https://github.com/otake-lab/otake-lab.github.io
    ```

- VScode等で編集

    ```bash 
    cd otake-lab.github.io
    code ./
    ```

- プレビュー

    ```bash
    jekyll s
    ```
    ブラウザで http://localhost:4000 を開くとプレビューできます

- 問題がなければ作ったファイルをcommit&pushします．

    ```bash
    git add .
    git commit -m "Add YYYY-MM-DD-title.md"
    git push
    ```

- GitHub上でpullrequestを出します．（4までできたら担当者に連絡してください．）

- masterにmergeされれば公開されます．