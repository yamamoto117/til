## Laravelとは
* 主にwebアプリケーションの作成に用いられるフレームワーク
* Symphonyと呼ばれる別のフレームワークを踏襲する形で設計開発された

## メリット
### 分業開発がしやすい
* Laravelは「MVC」というアーキテクチャを採用しているフレームワーク
* それぞれの機能別に独立しているので、分業体制で開発できる
* Model：データベースとの連携を担う
* View：ブラウザへの表示を司る
* Controller：指令や指示を司る
* LaravelのMVCには、通常のMVCに加えてコントローラーを制御する「ルーティング」という概念が加わる

### コードが分かりやすく学習コストが低い
* クセの少ないシンプルなコードで記述できる
* 開発の効率化を推し進める多くの機能が搭載されている(例えばバリデーションを自動化、データ操作を簡易化するマイグレーションなど)
* 簡単なコードであれば自動で作成してくれる

### プログラムの拡張性が高い
* 自動生成したコードのカスタマイズも容易に行える
* アジャイル型開発のように、細かい改修を行うことが前提の開発においても力を発揮しやすい

### 将来性が高い
* 人気の高さから細かいアップデートやプラグイン開発が行われている

## デメリット
* 処理速度に劣る点が目立つ(豊富な機能を搭載していることが災いしている)
* 自由度が高い反面、コードが煩雑化しやすい←分業でシステム開発をする場合は、コードの書き方に対してある程度のルールを設けておくのがおすすめ

## 活用例
* 従業員の勤怠を管理する業務システム
* 企業が運営するショッピングサイト
* 交通機関や宿泊施設の予約サイト
* 掲示板や口コミサイト
* SNSサービス
* ブログサービス
* チャットアプリ

## CakePHPとの違い
* 処理速度がやや遅い
* 柔軟性が高い

## 参考
* [Laravel（ララベル）とは？基礎知識とできることをわかりやすく解説](https://hnavi.co.jp/knowledge/blog/laravel/)
