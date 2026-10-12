# relation-app-practice

## 概要

COACHTECH 教材 Tutorial 9-5「リレーション ハンズオン演習」で作成した成果物です。
リレーションを使ったブログシステムを作成しました。
投稿にコメント（1対多）とタグ（多対多）を関連付けています。

## 使用技術

- PHP 8.x
- Laravel 10.x
- Eloquent ORM（hasMany / belongsTo / belongsToMany）
- MySQL
- Docker / Laravel Sail

## 学んだこと

- **リレーションの定義**  
  `hasMany`・`belongsTo`・`belongsToMany` を使い、投稿とコメントの1対多、投稿とタグの多対多の関係を定義しました。多対多では、中間テーブルを使ってデータを紐づける仕組みを学びました。

- **Eager LoadingとN+1問題**  
  `with()` を使って関連データをまとめて取得し、N+1問題を防ぐ方法を学びました。また、`withCount()` を使って、関連するコメントの件数を効率的に取得しました。

- **リレーションを使った検索**  
  `whereHas()` を使い、投稿に紐づくタグの名前を条件に絞り込む方法を学びました。リレーションを定義することで、関連テーブルのデータを条件にした検索ができることを理解しました。

## 動作確認

1. プロジェクトのディレクトリに移動する

    cd relation-app-practice

2. Laravel Sailを起動する

    ./vendor/bin/sail up -d

3. ブラウザで以下のURLにアクセスする

    http://localhost/posts

4. 投稿タイトルをクリックすると詳細ページが表示され、タグをクリックすると投稿を絞り込めます。

5. 確認後、Laravel Sailを停止する

    ./vendor/bin/sail down
