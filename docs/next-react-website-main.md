
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

## Chapter 2 コンポーネント

ここからブランチ(chapter2)を作成して，そのブランチにて開発を行う
chapter2 終了後にmainブランチへのマージを行う

```sh
$ git branch chapter2
$ git checkout chapter2
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


## Chapter 5 画像とアイコン


ブランチの作成

```sh
$ git branch chapter5
$ git checkout chapter5
$ git branch #確認用
```

Next13よりImageコンポーネントが新しくなった，従来のImageは next/legacy/Image

- layout属性とobjectFit属性が削除
- fill属性が追加
- layout='responsive' は size指定の上 styleでautoにする

#### responsive sample

```jsx
<Image
  src="/rocket.jpg"
  alt="空飛ぶロケット"
- layout="responsive"
  width={1980}
  height={1150}
+  sizes="100vw"    
+  style={{         
+    width: '100%',
+    height: 'auto',
+  }}
/>
```

### 5.1 Next.jsでの画像の取り扱い

- <img /> および next/image, next/legacy/image の<Image /> が使用できる

### 5.2 next/imageによる画像の最適化

- レスポンシブイメージのコード生成
- レイアウトシフト対応
- 遅延読み込み
- WebP対応
- SSGで使う場合は処理APIを外部に用意する

### 5.3 Imageコンポーネントの基本的な使い方

- 画像はpublicにおくか，任意の場所からimportして使うこともできる
- ディメンション属性でblurが使える

### 5.4 Imageコンポーネントの主なパラメータ

- layoutモードは現在 非推奨
- responsiveは  style={{width: '100%',height: 'auto',}} を使用
- fillはfill属性と style={{objectFit: 'cover'}} を使用
- fixedはlayout属性を外すだけ
- quality, priority, unoptimaized
- placeholder='blur' blurの表示
- style cssを設定

### 5.5 アバウトページに画像を表示する

- (p160) imageディレクトリを作成し，about.jpgを配置
- (p160) Aboutコンポーネントを編集して画像を追記
- (p160 - 161) Imageコンポーネントのプロパティを追記
- 画像を確認して commit

NEXT13でのresponsive Image

```jsx
<Image
  src={eyecatch}
  alt=''
  sizes='(min-width:1152px) 1152px, 100vw' 
  priority
  placeholder='blur'   
  style={{         
    width: '100%',
    height: 'auto',
    transition:0.2s
  }}
/>
```
### 5.6 ヒーローの画像を表示

- (p164) cube.jpgをimagesディレクトリに追加
- (p166) hero.module.cssを編集 imageクラスのwidthを設定
- (p165) Heroコンポーネントに画像を追加
- (p166) Heroコンポーネントにスタイルを追加
- (p168-p169) Imageコンポーネントにsize,priority, placeholderプロパティを追加
- 確認して git commit

```jsx
<Image
  src={cube}
  alt=''
  sizes='(min-width:1152px) 576px, (min-width:768px) 50vw, 100vw' 
  priority
  placeholder='blur'   
  style={{         
    width: '100%',
    height: 'auto',
  }}
/>

```

### 5.7 Font Awesomeのアイコンを使えるようにする

- (p170 - 171)fontawesomeの各種パッケージをインストール
- 全体設定用の _app.jsへ設定を追加

### 5.8 Font Awesomeの基本的な使い方

- (p173) アイコンを個別にインポートして使用する
- (p175) アイコンをグローバルにインポートして使用する
- (p176) アイコンのサイズと色をカスタマイズすることができる
- (p177) sizeプロパティ，styleプロパティ

### 5.9 アイコンを使ってソーシャルリンクメニューを作成する

- (p180) social.module.css 作成する
- (p179) Socialコンポーネントを作成する
- (p180) Socialコンポーネントを，FooterとContactコンポーネントに追加
- 確認して commit

### 5.10 アイコンのサイズをpropsで指定できるようにする

- (p183) social.module.cssを編集しfont-sizeに変数設定
- (p183) Socialコンポーネントのpropsを設定し外部から値を受け取る
- (p182) Contactコンポーネントを編集し値を送る
- 確認してcommit
- mainブランチにmerge