# conoha
- TerratermにてConohaのクラウドにUbuntuのインスタンスを立ち上げるツール
- ConohaのVMは初期ユーザはrootでsshもできるように設定されるが、Cloudinitを使い、別のユーザ、パスワードを追加している。
- Ubuntu20.1では通常のデプロイではIPv6が開始されないので、Cloudinitのnetplanを利用できるように修正している。
- 使い方
  1. Terraformインストール
  2. ConohaのAPI利用を開始し、username, user_password, tenant_id, api_urlを取得する。
  3. デプロイするUbuntの初期設定を./config/ubuntu-userdata.txtを編集して変更する。
  4. terraform初期化
     ```
     $ terraform init
     ```
  5. terraformデプロイ
     ```
     $ terraform apply \
      -var 'user_name=xxxx' \
      -var 'user_pass=xxxx' \
      -var 'tenant_id=xxxx' \
      -var 'api_identity_url=xxxx \'
      -var 'public_key_path=xxxx'
     ```

