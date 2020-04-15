# 必見！SEOに強くなるHTML文書の作成法

## 今だからこそはっきりさせておきたいHTML構造
可能な限り最低限のシンプルな情報にまとめますので、
深く知りたい方は各自ググって調べてみてください。

### DOCTYPE
HTML5では、以下のようなシンプルな記述となります。大文字と小文字は区別されません。

```html
<!DOCTYPE HTML>
```

HTML 4.01では、DOCTYPE宣言は以下のように記述していました。

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```

### headタグ内

#### charset
charsetは文字コードの種類を指定する
主流はUTF-8を使用することが多くHTML5ではこちらが推奨されています。

```html:実際のコード
<meta charset="utf-8">
```

#### viewport
viewportとは仮想ウィンドウのこと。

つまり
`<meta name="viewport" content="width=480">`とあったとすると
ブラウザ画面に480pxのモニターを置くということです。

`content="width=device-width`にすることで
モニター幅 = デバイス幅になるので、デバイスによって見え方を最適化する
レスポンシブデザインが可能になります。

```html:実際のコード
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

#### titleタグ
SEOにおいて最重要項目
CTR（クリック率）を上げるためにベネフィット（価値）や選定キーワードを30文字くらいです。
モバイルでは20文字くらいで切れてしまうので、後方は切れても内容がわかるように、
前方に重要キーワードを配置。
[文字カウント](http://www1.odn.ne.jp/megukuma/count.htm)

```html:実際のコード
<title>SEO Blog | SEOに強くなるためのブログを解説</title>
```

#### description
descriptionはタイトル下に出てくる説明。
こちらもタイトル同様、ベネフィットや選定キーワードを盛り込むことでCTR率を高める効果があります。
80〜120文字くらいだが50文字くらいがユーザーにみられる目安。

```html:実際のコード
<meta name="description" content="Webサイトの概要を記入">
```
（注）titleやdescriptionは複数ページでの内容の重複はGoogleが嫌うので変更するかnoindex処理で対応

#### canonical
`https://example.com`も`https://example.com/index.html`は
同じページではあるが違うページとして判別される。
それを回避するためにcanonical属性に正規URLを書くことで対応できます。

```html:実際のコード
<link rel="canonical" href="https://example.com">
```

### bodyタグ内

#### h1タグ
h1タグもtitleタグ同様めちゃくちゃ重要です。
・1ページ = 1個
・キーワードを含める
・h2-h6は可能な限りキーワードを含ませることでテーマの強調・統一性を保てます
・数字の順番通りに入れる

```html:実際のコード
<h1>main title</h1>
```

#### HTML構造タグを正しく使う
・header - 本でいう表紙
・nav - ナビゲーション
・main - コンテンツ部分（1ページ = 1個）
・article - mainの中に書き、ブログ記事の場合利用する（1ページ = 1個）
・section - main > section or main > article > section (複数つけていく)
・aside - サイドバーなど副次的な情報を出すのに利用
・footer - 本でいう背表紙
・strong - 強調させたい文字につける
・img - alt属性は必ずつけて説明文を書く
・a - URLリンク
・ul > li - 数字なしリスト
・ol > li - 数字ありリスト
・div - これ自体に意味を持たない装飾用のためのタグ　主にflexboxなどレイアウト調整に利用（block要素）
・span - div同様装飾用のためのタグ（inline要素）
etc