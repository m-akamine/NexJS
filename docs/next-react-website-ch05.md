# 作って学ぶ Next.js/React Webサイト構築

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