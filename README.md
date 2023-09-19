# atcoder-python-template

AtCoder用Python DevContainer環境

## Features

- [VSCode](https://code.visualstudio.com/)のDevContainer機能を用いたローカルから完全分離された仮想環境の提供
- [atcoder-cli](https://github.com/Tatamo/atcoder-cli)と[oj](https://github.com/online-judge-tools/oj)を用いた解答用ファイル生成、ローカルでのテストケースチェック、提出
- [poethepoet](https://github.com/nat-n/poethepoet)による共通化されたコマンドの提供

## Usage

### 初期設定

#### DockerとVSCodeのインストール

- [Docker](https://www.docker.com/)と[VSCode](https://code.visualstudio.com/)をインストール
- VSCodeに[Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)拡張機能をインストール

#### Dockerイメージの取得

- 以下のコマンドを実行し、Dockerイメージをpull

```
docker pull liebemagi/atcoder-python:latest
```

#### 開発コンテナを起動

- `Use this template`をクリックし、自身のリポジトリを作成し、ローカルにクローン
- クローンしたディレクトリをVSCodeで開き、右下に出てくるポップアップの「コンテナーで再度開く」をクリック

#### accとojにログイン

開発コンテナ内のターミナルで実行

- atcoder-cliのログイン

```
acc login
```

- ojのログイン

```
oj login https://atcoder.jp/
```

### 使い方

#### コンテスト用解答ファイルの生成 (`new`, `n`)

```
poe new [contestID]
```

#### テストケースのローカルチェック (`test`, `t`)

```
poe test [contestID] [taskID]
```

#### 提出 (`submit`, `s`)

```
poe submit [contestID] [taskID]
```

デフォルトではPyPyとして提出されるが、CPythonで提出したい場合は以下の通り

```
poe submit [contestID] [taskID] cpython
```

### テンプレートファイルの編集

`config/acc/python/main.py`の中身を変更することで、`new`コマンド実行時に展開される`main.py`の内容を編集可
