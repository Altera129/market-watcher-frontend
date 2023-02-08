# フロントエンド開発環境構築手順
この説明書では、フロントエンド開発環境をDockerで構築する方法を説明します。

## 前提条件
* Dockerがインストールされていること
* package.jsonが存在すること
## 手順
1. このリポジトリをクローンする
    ```
    git clone [repository-url]
    ```
1. フロントエンド開発環境のDockerイメージを作成する
    ```
    docker build -t [image-name] -f .docker/Dockerfile .
    ```
1. Dockerコンテナを起動する
    ```
    docker run -it --name [container-name] -v "$(pwd)/frontend:/app/frontend" -p 3000:3000 [image-name]
    ```
1. ブラウザでアクセスする
    ```
    http://localhost:3000
    ```
   これで、フロントエンド開発環境にアクセスすることができます。

# package.jsonの変更方法 (Docker環境)
1. Dockerコンテナに接続します
    ```
    docker exec -it [container_name] bash
    ```
1. frontendフォルダに移動します
    ```
    cd frontend
    ```
3. 新しいパッケージをインストールします
    ```
    npm install [new_package]
    ```
4. 依存関係をアップデートするために次のコマンドを実行します
    ```
    npm install
    ```