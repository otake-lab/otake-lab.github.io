# Otake-lab.site

## サイト構成
[jekyll](http://jekyllrb-ja.github.io/)という静的サイトジェネレータを使用しています．

```
index.html                          # トップページ
    |
    |- _posts
    |    |- 2020-06-23-title.md     # markdown形式のニュース
    |    
    |- member.html                  # 研究室に在籍する人のリスト
    |- news.html                    # ニュース
    |- study.html                   # 研究内容
    |- contact.html                 # 連絡先
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