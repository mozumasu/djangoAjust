# 2024-09-21-AWSなんてこわくないもん！2nd Season

## [Mermaid](https://mermaid.js.org/) Diagram Example

```mermaid
sequenceDiagram
    participant 開発者
    participant ローカルリポジトリ
    participant リモートリポジトリ

    開発者->>リモートリポジトリ: GitHub上でリポジトリを確認
    開発者->>ローカルリポジトリ: git clone [リモートURL]
    ローカルリポジトリ-->>開発者: リモートリポジトリをローカルにコピー
    開発者->>ローカルリポジトリ: git branch 新しいブランチ名
    開発者->>ローカルリポジトリ: git checkout 新しいブランチ名
    開発者->>ローカルリポジトリ: 作業開始
    開発者->>ローカルリポジトリ: ファイルを編集
    開発者->>ローカルリポジトリ: git add 変更したファイル
    開発者->>ローカルリポジトリ: git commit -m "変更内容の説明"
    ローカルリポジトリ-->>開発者: 変更をコミット
    開発者->>リモートリポジトリ: git push origin 新しいブランチ名
    開発者->>リモートリポジトリ: GitHub上でプルリクエストを作成
    リモートリポジトリ->>開発者: プルリクエストの承認
    開発者->>リモートリポジトリ: マージ
    リモートリポジトリ-->>開発者: 変更がマスターブランチに反映
```

## dockerの起動

1. [colima](https://github.com/abiosoft/colima)でdockerを起動

```shell
colima start
```

dockerのステータス確認

```shell
colima status
```

## アプリケーションの起動

````shell
```shell
docker-compose up -d
````

## dockerのサーバーに入る

```shell
docker exec -it djangoajust-web-1 bash
```

root@d579a2142892:/app#と表示されればOK

## コンテナの状態確認

```shell
docker ps -a
# または
docker container ls -a
```

## 選択したコンテナを削除

```shell
docker ps -a | awk '{print $1}' | fzf | xargs docker rm
```
