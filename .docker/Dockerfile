# 使用するNode.jsのイメージを指定
FROM node:14

# 作業ディレクトリを/app/frontendに変更
WORKDIR /app/frontend

# package.jsonとpackage-lock.jsonをコンテナにコピー
COPY frontend/package*.json ./

# npmパッケージをインストール、nodemonを追加
RUN npm install

# ホストのソースコードをコピー
COPY frontend .

EXPOSE 3000

# Dockerコンテナ起動時に実行するコマンド
CMD ["npm", "run", "start"]

# コンテナ内のsrcディレクトリをマウントする
VOLUME [ "/app/frontend" ]