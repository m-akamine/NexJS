# 作って学ぶ Next.js/React Webサイト構築

## Chapter 1 React と JSX

### 1.1 Reactが必要となってきている理由

- (p17) HTML + CSS とJavaScriptの構成からJavaScriptメインへ
- (p18) Reactでのページ作成
- (p19) React要素とJSX

### 1.2 Next.jsによるWebサイト構築

- (p22) Next.jsはSSRベースのフレームワークだがSGを取り込むこともできる

### 1.3 Next.jsのプロジェクト作成

- (p23) ```$ npx create-next-app@latest```
- (p24) ```$ npm run dev```

### 1.4 プロジェクトのファイル構成を確認する

- (p28) BLOG/public/ ブラウザからアクセス可能
- (p28) BLOG/pages/  Webページを追加する(動的ルーティング)
- (p29) BLOG/packege.json 設定を書く

### 1.5 ページとなるファイルの中身を確認する

- (p31) Homeコンポーネントを作る(書き換える)

### 1.6 JSXのルールを確認する

- (p31) 最上位の要素は一つ
- (p34) React.Fragment
- (p35) 要素は閉じる
- (p35) classは予約語のため classNameで代替
- (p36) style属性は {{}} expression {} 複数行は () のなか

### 1.7 JSXでトップページの構成要素を記述する

- (p38) Homeを記述 header, main, footer のシンプル構成
- ```$ npm run dev```で表示を確認
- この段階で git commit -m 'chap1 finished

## GitHUB連携

- access token(repo)を作成する (Settings/Developer settings/Personal access token)
- $HOME/.netrcを作成する

```.netrc
machine github.com
login ログイン名
password アクセストークン
```

- GitHub上でrepositoryを作成する
- 作成したrepositoryにpushする

```sh
$ git remote add origin https://github.com/USER_NAME/REPOSITORY_NAME
$ git branch -M main
$ git push -u origin main
```
