---
title: "Zenn+GitHub連携 環境構築手順"
emoji: "🦔"
type: "idea" # tech: 技術記事 / idea: アイデア
topics: ["Zenn", "GitHub", "環境構築"]
published: false
---

# 概要
Zenn始めました!!  
GitHub連携の記事は色々あるのですが、Gitを使用したことなかったりWindowsで環境を構築したこともあってもう少し詳しい記載が欲しいと思いました。  
記述不足だと感じた点を備忘録としてまとめておきます。  

# 動作環境
OS  : Windows10 Pro 20H2

# GitHubのインストール
公式手順の[GitHubリポジトリでZennのコンテンツを管理する](https://zenn.dev/zenn/articles/connect-to-github)に記載のない内容を捕捉します。  

1. [GitHubのアカウントを作成する](https://crestadesign.org/github-account/)
2. [リポジトリを作成する](https://zenn.dev/zenn/articles/connect-to-github#1.-%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B) 
    :::message
    公開設定は記事を管理するリポジトリであればPublic、本を管理するリポジトリはPrivateを設定する
    :::
3. QuickSetupに表示されるリポジトリのURLリンクを記録しておく
  ![リポジトリのURL](/images/zenn_envconfig_git/RepogitoryURL.png)
    :::message
   リポジトリのQickSetupや既存のリポジトリを利用するためのコマンドラインが表示されるが、ここでは何もする必要はない。 
    :::

4. [ダッシュボードから連携する](https://zenn.dev/zenn/articles/connect-to-github#2.-%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%8B%E3%82%89%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B)

# Gitのインストール
1. [【Windows】Gitの環境を構築しよう!](https://prog-8.com/docs/git-env-win)の2章まで実施する
2. Zennを管理するフォルダを作成する
    エクスプローラからでもGitBashからのコマンドラインからでもどちらでも構いません。   
    コマンドラインの場合はcdコマンドでディレクトリを移動し、mkdirコマンドでフォルダを作成します。
3. GitBashで作成したフォルダに移動し、下記のコマンドを実行する
   XXXにはリポジトリのURLリンクを記載し、YYYはリポジトリ名となる
    ```bash
    git clone git@github.com:XXX.git

    cd YYY
    npm init --yes
    npm install zenn-cli
    npx zenn init
    ```

# コンテンツを管理する
- [記事・本の書き方](https://zenn.dev/zenn/articles/zenn-cli-guide)
- [画像のアップロード方法](https://zenn.dev/zenn/articles/deploy-github-images)
- [ZennのMarkdown記法一覧](https://zenn.dev/zenn/articles/markdown-guide)

# 記事を投稿する
- GitBash
  下記のコマンドを実行し、リモートリポジトリにデプロイする(記事を投稿する)
    ```bash
    git add XXX.md
    git commit -am 'コメント'
    git push
    ```
- GitHub Desktop
  コマンド操作はできる限り避けたい人はGUIツールも提供されています。
  [GitHub Desktopのインストールから使い方まで徹底解説！](https://crestadesign.org/github-desktop/)を参考にしてみてください

