# curl コマンドについて
コマンドでhttp/https通信が可能

## 1. コマンドオプション
### 1.1 insecure
ssl/tls通信のエラーメッセージを無視するオプション<br>
httpsの検証で失敗したら試してみる。
```
curl https://example.com/path/ --insecure
```

## 2. 技術検証
コマンドやオプションについて、検証した結果をまとめる
### 2.1 localhost宛の通信で任意のホスト名を指定する。
`https://example.com/path/`や`http://example.com/path/`からしか受け取らない場合、以下方法で対応できる。<br>
```
# -H オプションを使用する場合。(Header情報の追加)
curl http://localhost/path/ -H "Host: example.com"

# hostsに登録する場合
# hostsにlocalhostのipのところに「example.com」を追加して実行する。
curl http://example.com/path/
```
