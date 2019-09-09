# We Love Virtual Machines
仮想環境をより便利に使うツールたち

---

## 自己紹介

- 渡邊 崇 <!-- .element: class="fragment" data-fragment-index="1" -->
- 0x2c歳 <!-- .element: class="fragment" data-fragment-index="2" -->
- 入社3ヶ月目 <!-- .element: class="fragment" data-fragment-index="3" -->

---

## ひと昔前のWeb開発での辛さ

### 開発中の確認用に本番用やステージング用とは別のサーバをたててアップロード

---

## マシン代と電気代でお財布に優しくない <!-- .element: class="fragment" data-fragment-index="1" -->
## 構築が面倒 <!-- .element: class="fragment" data-fragment-index="2" -->
## 複数人で共用してるとデグレがこわい <!-- .element: class="fragment" data-fragment-index="3" -->

<aside class="note">
SubversionやGitで管理してても、Gitが使えない人は何も考えずにファイルを上げる
</aside>

---

### 時代は変わった

- CPUの仮想化支援と多コア多スレッド化 <!-- .element: class="fragment" data-fragment-index="1" -->
- SSDやメモリの大容量化と価格低下 <!-- .element: class="fragment" data-fragment-index="2" -->

<aside class="note">
仮想化支援機能のついたマルチコアCPU、メモリ8GBぐらいは最低限の人権だと思っています
</aside>

---

### 仮想化環境下での開発のメリット
- 豊富なテンプレート <!-- .element: class="fragment" data-fragment-index="1" -->
- プロビジョニングによるカスタマイズの自動化 <!-- .element: class="fragment" data-fragment-index="2" -->
- 設定やプロビジョニング関連ファイルは基本テキスト <!-- .element: class="fragment" data-fragment-index="3" -->
  - gitで管理してればどこでも同じ環境を作れる <!-- .element: class="fragment" data-fragment-index="4" -->
  - 「秘伝のタレ」を回避できる <!-- .element: class="fragment" data-fragment-index="5" -->
- 手軽に作れて手軽に壊せるのは初期の試行錯誤には大きなメリット <!-- .element: class="fragment" data-fragment-index="6" -->

---

### 例

[https://github.com/takwat/vagrant-lamp](https://github.com/takwat/vagrant-lamp)

---

## 個人的に注目の仮想化ソフト
### WSL(Windows Subsystem for Linux)
- 起動が早くWindowsのアプリ感覚でUbuntuが立ち上がるのは楽しい <!-- .element: class="fragment" data-fragment-index="1" -->
- でも現状では結構残念ポイントが多い <!-- .element: class="fragment" data-fragment-index="2" -->
- 次期Windows 10の大規模アップデートでMSが本気を出して作ったLinuxカーネルに乗る <!-- .element: class="fragment" data-fragment-index="3" -->
- かなりパフォーマンスが上がって残念ポイントが解決されているらしい <!-- .element: class="fragment" data-fragment-index="4" -->

---

### 仮想環境も解決できない辛み(1)

<img src="img/rsync.jpg" class="stretch">

<aside class="note">
ホスト側とゲスト側で同じ環境を2つも揃えないといけないのが辛い
</aside>

---

### 仮想環境も解決できない辛み(2)

<img src="img/vboxsf.jpg" class="stretch">

<aside class="note">
ホスト側からいじるファイルとゲストから参照するファイルが一元化はされたもののvboxsfの場合は参照が遅い
それでいてホスト環境にもPHPを入れないとだめというのは解決されず
</aside>

---

### Remote Developmentで解決

<img src="img/remote.jpg" class="stretch">

<aside class="note">
- エディタのUI部分だけホスト(Windows/Mac)側で動いてますという形
- 編集対象はゲスト側のローカルファイル
- gitやPHPの実行エンジン(XDebug含む)などはゲスト側で動いているものを使う
- ホスト側にはVirtualBox / Vagrant / VSCode関連以外の開発ツールは一切インストール不要
- 実行・停止の指令と動作状態のモニタリングをサーバ側にインストールされたnode.js製のプラグインなどで行ってホスト側に転送
- SSHぶんのオーバーヘッドはあるもののそこまで気にならない
</aside>

---

## ngrok





---
