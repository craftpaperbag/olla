# olla

Simple chat tool for ollama.
シンプルなOllama向けチャットツールです。

## Local testing with Docker Compose

The repository includes a lightweight Ollama setup so you can bring up a test
server with a single command:
このリポジトリには軽量なOllama環境が含まれており、次のワンコマンドでテスト用サーバーを立ち上げられます。

```bash
docker compose up
```

This starts the official `ollama/ollama` image and automatically pulls the
`llama3.2:1b` model, which is small enough to run on CPU-only machines. The
compose file also constrains parallelism and CPU threads to keep resource usage
low for slower PCs.
これにより公式イメージ`ollama/ollama`が起動し、CPUのみのマシンでも動作する軽量モデル`llama3.2:1b`を自動で取得します。
composeファイルでは並列数とCPUスレッド数を抑えて、性能の低いPCでもリソース使用を低く保つようにしています。

## Serve the UI with one Docker command

To host `index.html` from a containerized web server, run:
単一のコマンドで`index.html`を配信するWebサーバーのコンテナを起動するには、次を実行します。

```bash
docker compose up web
```

The `olla-web` service uses `nginx:alpine` and binds port `8080` on the host to
port `80` in the container so you can open http://localhost:8080 and view the UI.
`olla-web`サービスは`nginx:alpine`を用いてコンテナ内の80番ポートをホストの8080番に公開し、
http://localhost:8080 からUIにアクセスできます。
