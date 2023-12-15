# 作って学ぶ Next.js/React Webサイト構築

## Chapter 2 コンポーネント

ここからブランチ(chapter2)を作成して，そのブランチにて開発を行う
chapter2 終了後にmainブランチへのマージを行う

```sh
$ git branch chapter2
$ git switch chapter2
$ git branch #確認用
```

### 2.1 コンポーネントを使う

- (p42) 関数コンポーネントとClassコンポーネント
- (p43) コンポーネント名は大文字から

### 2.2 コンポーネントのprops

props(オブジェクトになった引数)

- (p44) propsへの値の渡し方
- (p45) props.children 理解
- (p47) propsはReadOnly

### 2.3 コンポーネントを作る

- (p48) コンポーネントの分け方(共通のものや，構造が同じものに着目する)
- (p49) compornents ディレクトリを作成する
- (p49) Header, Hero, Footer コンポーネントを作成する
- (p50) Header, Hero, Footer コンポーネントをHomeコンポーネントで使用する
- ```$ npm run dev``` で確認し ```$ git commit -m '2.3 base'```

### 2.4 絶対パスでインポートできるようにする

- (p51) BLOG/jsconfig.jsonで絶対パスを記述

### 2.5 ヘッダーと降った-をLayoutコンポーネントで管理

- (p54) Layoutコンポーネントを作成
- (p55) HomeコンポーネントでLayoutコンポーネントを使用
- ```$ npm run dev``` で確認し ```git commit -m '2.5 layout'```

### 2.6 カスタムAppコンポーネントでLayoutを全ページに入れる

pages直下に_app.jsというコンポーネントで全ページの共通設定を行う

- (p57) _app.jsを作成してLayoutコンポーネントでChildrenをWrapする
- (p57) Homeコンポーネントを編集しLayoutを削除する
- ```$ npm run dev``` で確認し ```git commit -m '2.6 layout'```

### 2.7 ページを増やす

- (p58) pages直下にblogディレクトリを作成しindex.jsを作成
- (p58) about.jsを作成
- ```$ npm run dev``` で確認し ```git commit -m '2.7 about, blog'```

### 2.8 ヒーローのテキストをpropsでページごとに変更

- (p58) hero.jsを編集し，propsから値を受け取る
- (p59) Home, About, Blogコンポーネントを編集 

### 2.9 ヒーローの画像をpropsでオンにする

- (p63) hero.jsを編集してフラグ(imageOn)を受け取る
- (p62) Homeコンポーネントを編集，フラグ(imageOn)を渡す
- Homeページのみに画像の文字が出たことを確認
- git commit -m '2.9 propsから値を渡す'```

### 2.10 next/linkのLinkコンポーネントでページ間のリンクを作成する

next13よりLinkコンポーネントが新しくなりaタグが使用禁止
aタグを使いたい場合は<Link legacyBehavior>を使用

- (p67) logo.jsを作成
- (p68) nav.jsを作成
- (p69) Header, Footerコンポーネントを編集
- リンクが表示され，各リンクが活きていることを確認
- git commit -m 'chapter2 finished'

