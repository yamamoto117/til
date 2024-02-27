## Bladeとは
* 簡単な構文を使ってHTMLを生成するためのテンプレートエンジン
* Bladeテンプレートは、「.blade.php」の拡張子を持ち、PHPコードを含むことができる
* ただし、PHPコードは「@」記号で始まるBladeディレクティブを使用して表現される
* これにより、BladeはPHPの可読性を向上させることができる

## 特徴
* コードの読みやすさ
* 複数のテンプレートを継承して再利用することができる柔軟性

## コード例(レイアウト)
resources/views/components/layouts/default.blade.php
```
<!DOCTYPE html>
<html lang="ja">
  <head>
    ...
  </head>
  <body>
    <header>
      <h1>{{ $title ?? 'My Site'}}</h1>
    </header>
    <main>{{ $slot }}</main>
  </body>
</html>
```

resources/views/my-page.blade.php
```
<x-layouts.default>
  <x-slot:title>My Page</x-slot:title>
  コンテンツをここに配置します。
</x-layouts.default>
```

結果
```
<!DOCTYPE html>
<html lang="ja">
  <head>
    ...
  </head>
  <body>
    <header>
      <h1>My Page</h1>
    </header>
    <main>ここにコンテンツを配置します。</main>
  </body>
</html>
```

* x-layouts.default：layoutsディレクトリの下のdefault.blade.phpを読み込め、という命令
* x-parts.message：partsディレクトリの下のmessage.blade.phpを読み込め、という命令

## コード例(ループ変数)
```
<ul>
  @foreach ($items as $item)
    @if ($loop->first)
  		<li class="list-item first-item">{{ $item }}</li>
    @elseif ($loop->last)
      <li class="list-item last-item">{{ $item }}</li>
    @else
      <li class="list-item">{{ $item }}</li>
    @endif
  @endforeach
</ul>
```

## コード例(CSRF対策)
Cross-Site Request Forgeries
* 他のサイト上にあるページから不正なリクエストを送ることができてしまう脆弱性
* この脆弱性があると、ユーザーが意図しない情報を送信/受信してしまうことになる

```
<form method="post" action="/store">
  @csrf
</form>
```

@csrf とだけ書けば、以下のようなタグを自動で生成してくれる

```
<form method="post" action="/store">
  <input type="hidden" name="_token" value="2e4WckkUOHHYaOb1smJAXkq9atsxdVA21TJfqaiv">
</form>
```

データの送信を受け付ける側は、この _token という名前を持つ正しいトークンが一緒に送られてこなければリクエストを拒否するようになっているので、CSRFの攻撃を防ぐことができる

## 参考
* [PHPのLaravelとは？特徴や向いているプロジェクト、使い方を詳しく解説](https://cmc-japan.co.jp/blog/what-is-laravel/)
