# Mini Book Management System

メトロポリタン美術館の所属作品を検索するシステムです。  
Flask＋Elasticsearchで動作しています。  
内部では、The Metropolitan Museum of Art Collection API を呼び出しています。

## Requirement

- Java 1.8
    - Elasticsearchを動作させるのに必要
    - JREではなくJDKにしないと動作しない
- Elasticsearch6.3
    - 次の2つのプラグインをインストールしておいてください
        - ICU Analysis
        - Japanese (Kuromoji) Analysis
    - http://localhost:9200 でアクセスできることを確認しておいてください
- pip install elasticsearch
- pip install Flask

## Usage

### Elasticseachの初期化

- ElasticsearchのINDEXを定義します。（RDBでのTable作成に相当）
    - python initialize.py
    - 「setting.json」「mapping.json」を参照しています
    - すでに、当該INDEXが作成されていた場合には、そのINDEXは削除されます

### Flask＋アプリの実行

#### Flask起動  

- python app.py

次のような画面が出れば、成功です
```
 * Serving Flask app "app" (lazy loading)
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
```  
CTRL+Cが入力されるまで、Flaskが動作し続けます

#### アプリへのアクセス

- ブラウザで次のURLにアクセスしてください
    - http://localhost:8080

次のような画面が出れば成功です
![serch](https://user-images.githubusercontent.com/45332421/50080215-f1cce900-022e-11e9-8119-6fc956d8b62b.JPG)


### アプリを使う

1. 好きな番号を入力して「serch」ボタンを押します
![inputnumber](https://user-images.githubusercontent.com/45332421/50080119-baf6d300-022e-11e9-85fd-4633f72830d0.JPG)


2. 検索結果が表示されます
![result](https://user-images.githubusercontent.com/45332421/50080191-e4176380-022e-11e9-93da-5f0d23129a3c.JPG)


## Authors

- [leadinge-nakagawa](https://github.com/leadinge-nakagawa/METMuseum)
