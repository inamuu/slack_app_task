Slack App Task Tool
===

### まずはじめに

API Gatewayを作成する

1. REST API を選択
2. プロトコルはREST， 新しいAPIを選択
3. 「slack-app-api-endpoint」という名称にする
4. エンドポイントタイプはリージョン
5. 「APIの作成」をクリック

パスを変えたかったらリソースを作成する
1. リソースを作成
2. パスになる名前を設定

メソッドを作成
1. POST
2. 統合タイプはLambda関数
3. Lambdaプロキシ統合の使用にチェック
4. Lambdaリージョンは ap-northeast-1
5. Lambda関数名に slack-app-task-took
6. 権限が求められるのでOK

APIのデプロイ
1. APIをデプロイ
2. ステージ名は v1

POSTを投げてみる
```sh
curl -XPOST https://エンドポイント名/v1/task -d '{ "key" : "test" }'
```

bodyに上記値が入ってこればOK.

### セットアップ

```sh
python -m venv ~/.venv/slack_app_task
source ~/.venv/slack_app_task/bin/activate
pip install -r requirements.txt
```

```sh
cp lambda.json.sample lambda.json
```

### デプロイ

```sh
lambda-uploader --profile PROFILE_NAME
```

### ドキュメント

https://dev.classmethod.jp/cloud/aws/serverless-framework-with-python-3-6/

