Slack App Task Tool
===

### Setup

```sh
python -m venv ~/.venv/slack_app_task
source ~/.venv/slack_app_task/bin/activate
pip install -r requirements.txt
```

```sh
cp lambda.json.sample lambda.json
```

### Deploy

```sh
lambda-uploader --profile PROFILE_NAME
```

### Document

https://dev.classmethod.jp/cloud/aws/serverless-framework-with-python-3-6/
