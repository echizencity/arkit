<!-- 
# 表示タイトル by craftARt

- [表示タイトル](https://username.github.io/reponame)  

## craftARt とは？

“craftARt” は、

- **craft**（手仕事・手作り）
- **AR**（拡張現実）
- **art**（芸術・美術）

の3つを組み合わせた造語です。  
地域の文化財やものづくりを、AR技術で新しい形に再発信することを目指すWebアプリです。  

本アプリは[craftARt-kit](https://github.com/echizencity/craftARt-kit)を使って作成しました。
-->

# craftARt 越前

- [craftARt-kit](https://echizencity.github.io/craftARt-kit/)

## craftARt とは？

“craftARt” は、

- **craft**（手仕事・手作り）
- **AR**（拡張現実）
- **art**（芸術・美術）

の3つを組み合わせた造語です。  
地域の文化財やものづくりを、AR技術で新しい形に再発信することを目指すWebアプリです。  

本アプリは[Code for Fukui](https://code4fukui.github.io)の協力で作成しました。

## craftARt 越前 とは？

”craftARt 越前”は、  
**越前市版のcraftARt**であり、地域文化を拡張現実（AR）として再発信する取り組みです。

## 内容

### アプリ種別

| アプリ名           | 用途                         | 端末 | HTML |
|--------------------|------------------------------|--------|--------|
| **craftARt Lite**  | ヘッドセット向け軽量ビューア | ヘッドセット | `/headset.html` |
| **craftARt Event** | イベント向けAR体験    | スマホ | `/event.html` |
| **craftARt Go**    | 簡易型ARビューア | スマホ | `/go.html` |

※`index.html`でXR対応デバイスであれば`headset.html`へ、XR対応デバイスでなければ`go.html`へ分岐しています

### 導入キット

地域や団体で craftARt を活用いただくための導入キットはこちら：

- **[craftARt-kit](https://github.com/echizencity/craftARt-kit)**  
  GitHub Pages をベースに、誰でも無料・簡単にAR展示が始められる導入キットです。

### 使用ライブラリ

- [model-viewer](https://modelviewer.dev/)
- [egxr.js](https://github.com/code4fukui/egxr.js/blob/main/egxr.js) （Code for Fukui）
- [threeutil.js](https://github.com/code4fukui/vr-lenspark/blob/main/threeutil.js) （Code for Fukui）

### ライセンス

このプロジェクトは **MITライセンス** のもとで公開されています。  
ご自由に利用・改変・再配布が可能です。

---

## 0. はじめに

### 0-1. このプロジェクトでできること

- スマートフォンだけでAR展示を作成・公開できる
- GitHub Pages を使ってWebで公開
- スキャン → 軽量化 → アップロード の3ステップで完了
- PCやアプリ開発の知識は不要！

### 0-2. 必要なもの

- スマートフォン（iOS または AR対応 Android）
- Scaniverse アプリ（または代替スキャンアプリ）
- GitHub アカウント
- 3D化したい対象物（文化財、地域資源、作品など）

### 0-3. 特徴

- PC不要：スマホだけで完結  
- スキル不要：誰でも3DコンテンツをAR化
- 導入例：文化・観光・教育などにすぐ使える  

### 0-4. PC を併用する場合

craftARt は、PCがなくても **スマートフォンだけで、工程をすべて行うことができます。**

#### テキスト編集は PC でも OK！

- `README.md` や `models.csv` の編集など、**細かいテキスト作業は PC での編集が快適**です。
- ただし、スマホでも十分に対応可能です。

#### 快適な使い方
> モデルの準備からアップロードまで（[2. Scaniverseで3Dモデル作成](#2-scaniverseで3dモデル作成) から [4.2 ファイルをアップロード](#4-2-ファイルをアップロード) まで）はスマホで、  
> その他の作業（READMEやCSVファイルの編集、QRコードの作成等）は PC で行うのが快適です。

---

## 1. GitHub リポジトリを準備

### 1-1. GitHub アカウントを作成

- https://github.com にアクセスし、アカウントを登録
- ユーザー名とメールアドレスを設定

### 1-2. GitHubモバイルサイトにログイン

### 1-3. 制作キットを自分のリポジトリにコピー

- 「craftARt-kit」のGitHubリポジトリを開く  
  https://www.github.com/echizencity/craftARt-kit
- [Fork]を選択
- 「Repository name」を変更: `craftARt-kit` → `reponame`
- [Create fork]で自分のアカウント下に作業用リポジトリを作成

### 1-4. README.md を修正

Forkしたリポジトリの `README.md` を開き、[…] → [Edit in place]  
次の4点を修正する

- **コメントアウトを解除:**  
  1行目の `<!--` と、18行目の `-->` を削除する  
- **不要な説明文を削除:**  
  また、20行目以降（最後まで）の説明文を削除する  
- **表示タイトルを変更:**  
  2行目と4行目の `表示タイトル` を、**自分の展示タイトル**に変更する  
- **公開URLのパスを修正:**  
  4行目にあるURL内の `username` と `reponame` を、それぞれ**GitHubアカウント名と、作成したリポジトリ名**に書き換える  

編集後、[Commit changes] → [Commit changes]で保存

### 1-5. GitHub Pages を有効化

- […] → [Settings] → [Pages] → 「Branch」の“None”を“main”にして [Save]
- 約1分後に公開URLが発行される  
  `https://username.github.io/reponame`

---

## 2. Scaniverseで3Dモデル作成

### 2-1. Scaniverseアプリ（または類似アプリ）を起動

- [+] → [メッシュ] → オブジェクトサイズを指定 → [●]
- 対象物の周囲をゆっくり撮影  
  光の反射や背景ノイズに注意して撮影
- [●]で撮影終了 → 処理モードを選択 → 1~2分待つ → [保存]

### 2-2. クロップ（切り取り）

- [編集] → [トリミング]で、不要な床や背景をカット

### 2-3. glb形式でエクスポート

- [共有] → [モデルのエクスポート]を選択  
  **エクスポート形式は `.glb`（推奨）**
- [ファイルに保存]を選択  
  ファイル名を以下の形式で変更（日本語・スペースNG）

例：`hajiki01.glb`,`sueki03.glb`

---

## 3. gltfbeautyで軽量化

**モデルのファイルサイズが大きい場合（目安：15MB以上）は、Gltfbeautyを使って軽量化。表示スピードや安定性を確保します。**

### 3-1. モバイル対応 gltfbeauty にアクセス

- 軽量化ツール：gltfbeauty（Code for Fukui）  
  https://code4fukui.github.io/gltfbeauty/

### 3-2. モデルファイルを選んで読み込み

- テクスチャーサイズなどを調整する
- 「ファイル選択」から.glbファイルを選択  
  → 自動で軽量化されたファイルがダウンロードされる

---

## 4. GitHubにアップロード

### 4-1. GitHubモバイルサイトから、「models」フォルダを開く

### 4-2. ファイルをアップロード

- […] → 「Upload files」→「choose your files」  
  → スマホから（軽量化済み）glbファイルをアップ
- 元々あった「sample.glb」は削除:  
  → […] → [Delete file] → [Commit changes] → [Commit changes]

### 4-3. models.csv を編集

- 「models」フォルダから上の階層「reponame」フォルダに移動
- CSVファイル（models.csv）を開き、[…] → [Edit in place]  
以下のように入力する：

|path|name|description|url|
|----|----|----|----|
|`./models/hajiki01.glb`|土師器|（任意）|（任意）|
|`./models/sueki03.glb`|須恵器|（任意）|（任意）|

- 半角カンマ区切り
- 1行目は項目名:  
  `path` , `name` , `description` , `url` のままで変更しない
- 2行目以降がデータ内容:  
  `path` は3Dモデルの置いてある場所（必須）  
  `name` は3Dモデルの名称（必須）  
  `description` , `url` は備考とリンク先（任意）。入力しない場合も、`name` の後ろの `“,,”` は消さない
- 編集後、[Commit changes] → [Commit changes]で保存

---

## 5. 公開と動作確認

### 5-1. GitHub Pagesが自動更新

- 公開URLにアクセスし、ページが更新されているか確認：

|名称|端末|URL|
|----|----|----|
|craftARt Event|スマホ|`https://username.github.io/reponame/event.html`|
|craftARt Go|スマホ|`https://username.github.io/reponame/go.html`|
|craftARt Lite|ヘッドセット|`https://username.github.io/reponame/headset.html`|

### 5-2. 動作確認（スマホ）

- ARボタンで起動するか確認（AR対応機種で）
- モデルの読み込み・サイズに問題がないか確認
- Android端末の場合はARCore対応かを確認

### 5-3. 動作確認（ヘッドセット）

- ARボタンで起動するか確認
- モデルの読み込み・表示サイズに問題がないか確認

---

## 6. QRコード作成と印刷

### 6-1. QRコード作成ページへ

- おすすめツール：QRコード作成（jig.jp）  
  https://fukuno.jig.jp/app/util/qrmaker/

- 作成対象URL：  
  （Event）`https://username.github.io/reponame/event.html`  
  （Go）`https://username.github.io/reponame/`

  ※`index.html`でXR対応デバイスでなければ`go.html`へ分岐しています

### 6-2. QRコードを印刷・配布

- チラシ・ポスター・会場パネルなどに貼り出してAR体験スタート！

---

## 補足

### forkだけだと見た目が同じなので区別したい場合：

#### 1. 固有名称に変更

- `headset.html`: 5行目, 11行目  
- `event.html`: 5行目, 194行目  
- `go.html`: 5行目, 135行目

※5行目はWebページのタイトル、他の行は表示されるタイトル

#### 2. GLBやAPPを指定

- `headset.html` の13行目がGLBファイルの場所、14行目がAPPの場所を指定している

`<!--     GLB: <a href="https://github.com/echizencity/opendata/tree/main/kokufuhakkutsu/">越前国府発掘プロジェクト</a><br> -->`  
`<!--     APP: <a href="https://github.com/echizencity/craftARt-kit/tree/main/">src on GitHub</a><br> -->`

↓コメントアウトを解除して、URL等を修正する

`GLB: <a href="https://github.com/username/reponame/tree/main/models/">〜〜〜〜</a><br>`  
`APP: <a href="https://github.com/username/reponame/tree/main/">src on GitHub</a><br>`


---

## まとめ

### 基本ステップ一覧

| ステップ | 操作内容                         | 使用アプリ／サービス                 | 備考                                       |
|----------|----------------------------------|--------------------------------------|--------------------------------------------|
| 1        | GitHub リポジトリを準備（初回のみ）  | GitHub                               | 最初に一度だけ必要                          |
| 2        | 3Dモデルを作成                     | Scaniverse（または類似のスキャンアプリ） | 新しいモデルを作るたびに実施                |
| 3        | gltfbeautyで軽量化（目安:15MB以上の場合）| gltfbeauty（Code for Fukui）         | `.glb` 形式に圧縮・最適化                   |
| 4        | GitHubにアップロード              | GitHub モバイルサイト                 | `models/` フォルダと `models.csv` を更新     |
| 5        | 公開と動作確認                    | スマホブラウザ                        | 公開URLで表示・動作チェック                |
| 6        | QRコード作成と印刷                | QRコードメーカー（jig.jp）            | URLが変わらない限り、再作成は不要          |

---

### 新しいモデルを追加・差し替えたいときは：

**ステップ 2 → 3 → 4 → 5** を繰り返すだけでOKです！
