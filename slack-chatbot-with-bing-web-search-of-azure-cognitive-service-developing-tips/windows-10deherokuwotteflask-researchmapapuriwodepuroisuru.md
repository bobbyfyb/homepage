---
description: Flask-researchmapプロジェクトのherokuにデプロイする方法
---

# Windows 10でHerokuを使ってFlask-researchmapアプリをデプロイする手順

### １．GithubからFlask-researchmapプロジェクトを自分のコンピュータにcloneする．

```text
git clone git@github.com:ISRTsukuba/flask-researchmap.git
```

### ２．プロジェクトの作業用ディレクトリにターミナル（PowerShellやCMD）を開いて、Herokuにログインする．

ターミナルに

```text
heroku login
```

を入力して、エンターキーを押したら、ブラウザにherokuのログインページが自動的に開かれて、ここにあるheroku loginボタンをクリックすると、Herokuにログインが完了．

### ３．ログインが出来たら次にHeroku appを作成する．

```text
heroku create <appname>
```

&lt;appname&gt;でHerokuアプリの名前を設定する．※ほかの人と被らない名前にしてください．

### 4.　作業用ディレクトリにrequirements.txtがあるのを確認する上で、Procfileを作成する

ProcfileとはHerokuがデプロイされたアプリを起動する際に実行するべきのコマンドを説明するファイルである．Procfileに

```text
web: gunicorn -b 0.0.0.0:$PORT app:app
```

を入力して、拡張子を付けずに作業用ディレクトリに保存する．ここでgunicornというpythonのhttp serverを使ったので、requirements.txtにgunicornの追加を忘れないでください．

### 5．Herokuにデプロイする

requirements.txtとProcfileが完了したら次はHerokuにデプロイを行う．

```text
git init
git add .
git commit -m "app deploy"
git push heroku master
```

ターミナルに上のコマンドを実行して、Herokuがデプロイを行う．完了したら

```text
heroku open
```

でデプロイされたアプリを確認できる．ブラウザにhttp://&lt;appname&gt;.herokuapp.comに行くもできる．



### 参考ページ：

{% embed url="https://qiita.com/osakasho/items/527421ec483052055b34" %}

{% embed url="https://devcenter.heroku.com/articles/getting-started-with-python\#provision-a-database" %}

{% embed url="https://devcenter.heroku.com/articles/flask-memcache" %}



