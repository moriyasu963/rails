# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## 開発環境構築

```
$ docker-compose build
```

## railsプロジェクトの作成

```
$ docker-compose run --rm web rails new .  \
--database=mysql \
--skip-coffee \
--skip-test \
--skip-bundle 
```

## デバッグ実行

```
$ docker-compose up --build
```

IntelliJ IDEのRuby Remote debugから

```
rdebug-ide --host 0.0.0.0 --port 1234 --dispatcher-port 26162 -- $COMMAND$ 
```

を実行




## railsコマンド実行

```
$ docker-compose run --rm web rails [コマンド]
```

例

```
DB作成
$ docker-compose run --rm web rails db:create
DBマイグレーション
$ docker-compose run --rm web rails db:migrate
RSpec作成
$ docker-compose run --rm web rails g rspec:install
```

## bundleコマンド実行

```
$ docker-compose run --rm web bundle exec [コマンド]
```

例

```
guard初期化
$ docker-compose run --rm web bundle exec guard init
guard実行
$ docker-compose run --rm web bundle exec guard
```