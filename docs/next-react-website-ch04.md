# 作って学ぶ Next.js/React Webサイト構築

## Chapter 4 レイアウトのスタイル

```sh
$ git checkout main
$ git branch #確認用
$ git merge chapter3
$ git push
```
新しくブランチを切りその上で開発する
```sh
$ git branch chapter4
$ git checkout chapter4
$ git branch #確認用 
```

### 4.1 共通したレイアウトのスタイルを用意する

- (p104) 両端揃え -- レスポンシブでも変化なし
- (p104) 横並び(基本形)
- (p104) 横並び(中央揃え) -- モバイルは縦並びに
- (p105) util.module.cssを作成
- git commit -m '4.1 util.module.css'

### 4.2 共通のスタイルでヘッダーのレイアウトを整える

- (p107) header.module.cssを編集 util.module.css のレイアウトをcomposeする
- (p106) HeaderコンポーネントにCSS適用
- git commit -m '4.2 header layout'

### 4.3 共通のスタイルでヒーローのレイアウトを整える

- (p109) hero.module.cssを編集 util.module.css のレイアウトをcomposeする
- (p108) HeroコンポーネントにCSS適用
- git commit -m '4.3 hero layout'

### 4.4 共通のスタイルでフッターのレイアウトを整える

- (p111) footer.module.cssを編集 util.module.css のレイアウトをcomposeする
- (p110) footerコンポーネントにCSS適用
- git commit -m '4.4 footer layout'

### 4.5 Containerコンポーネントで横幅を整える

- (p113) コンテナコンポーネント及びcontainer.module.cssを作成
- (p114) ヘッダー，フッターコンポーネントをコンテナコンポーネントでラップする
- (p116) container.module.cssを編集し，.largeクラスを追加
- (p116) コンテナコンポーネントのpropsを追加
- (p115) ヘッダーコンポーネンとからパラメータを渡す
- git commit -m '4.5 header,footerのwidth調整'
- (p117) Home, About, Blogをコンテナコンポーネントでラップする
- git commit -m '4.5 Home, About, Blogのwidth調整'
- (p118) Aboutコンポーネントに記事を追加
- git commit -m '4.5 記事を追加'

### 4.6 PostBodyコンポーネントで本文のレイアウトを整える

- (p121) post-body.module.cssを作成
- (p121) PostBodyコンポーネントを作成しCSSを適用
- (p122) PostBodyコンポーネントをAboutコンポーネントに適用
- git commit -m '4.6'

### 4.7 Contactコンポーネントでコンタクト情報を管理する

- (p126) contact.module.cssを作成する
- (p126) Contactコンポーネントを作成しCSSを適用
- (p127) コンタクトコンポーネントをAboutコンポーネントに追加
- git commit -m '4.7 Contact作成'

### 4.8 3つのコンポーネントで2段組のレイアウトを構成する

- (p132) two-column-module.cssを作成 sideBysideをcompose
- (p129 - 130) TwoColumn, TwoClolumnMain,TwoColumnSidebar コンポーネントを作成しCSS適用
- (p131) Aboutコンポーネントを上記コンポーネントで2段組みにする
- (p133) two-column-module.css 追記してサイドバーを右揃えにする
- (p134) two-column-module.css 追記してサイドバーを固定表示
- git commit -m '4.8 2段組レイアウト'

mainブランチにmergeしてpush
```sh
$ git checkout main
$ git branch #確認用
$ git merge chapter4
$ git push
```

