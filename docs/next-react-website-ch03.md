# 作って学ぶ Next.js/React Webサイト構築

## Chapter3 CSS Moduleとスタイル

ここでマージを行う，まずmainブランチに移動してそこでマージを行う
そして新たにchapter3を作成してその上で開発を行う

```sh
$ git checkout main
$ git branch #確認用
$ git merge chapter2
$ git push # githubと同期する
```

新しくブランチを切りその上で開発を進める
```sh
$ git branch chapter3
$ git checkout chapter3
$ git branch #確認用 
```

### 3.1 スタイルの適用方法

- (p72) グローバルスタイル _app.jsにインポートして使用
- (p72) CSS Module コンポーネントごとに設定 拡張子を module.cssとする
- (p73) CSS-in-JS コンポーネント内にjavascriptとして記述 いくつかの種類がある
- (p73) インラインスタイル

### 3.2 CSS Moduleの使い方

- (p74) hero.module.cssを作成
- (p74) Heroコンポーネントに適用
- (p76) 個別にクラスを指定できないケース
- (p77) 個別のクラスが指定されているケース
- (p78) composesを用いて合成する

### 3.3 グローバルスタイルを設定する

- (p82) _app.jsを編集，global.cssをimportする
- (p83-p87) global.cssを作成,編集する
- (p87) 表示が変わったことを確認して 
- git commit -m '3.3 global style'

### 3.4 コンポーネントのスタイルを設定

- 保守性や再利用のために見た目とレイアウトのスタイルを分けて作成する

### 3.5 ヒーローのテキストのスタイルを設定

- (p89) footer, header, hero, layout, logo, nav の CSS Modulesを作成
- (p91) hero.module.cssを記述
- (p90) Heroコンポーネントを編集してCSSを適用，確認
-  commit する

### 3.6 ロゴのスタイルをpropsで切り替える

- (p92) logo.module.cssを編集
- (p94) Logoコンポーネントを編集してCSSを適用
- (p93) Headerコンポーネントを編集してLogoコンポーネントに値を設定
-  commit する

### 3.7 ナビゲーションメニューとリンクのスタイルを指定する

- (p97) nav.module.css を編集
- (p96) Navコンポーネントを編集しCSSを適用し確認
- (p99) nav.module.css を編集しホバー時の設定を追加
- (p100)表示確認
- commit

