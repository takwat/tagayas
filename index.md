# We Love Virtual Machines
仮想環境をより便利に使うツールたち

---

## 自己紹介

- 渡邊 崇 <!-- .element: class="fragment" data-fragment-index="1" -->
- 0x2c歳 <!-- .element: class="fragment" data-fragment-index="2" -->
- 入社3ヶ月目 <!-- .element: class="fragment" data-fragment-index="3" -->
- 社内部活動 Qiita部所属 <!-- .element: class="fragment" data-fragment-index="4" -->
- https://qiita.com/_takwat/ <!-- .element: class="fragment" data-fragment-index="5" -->

---

## ここからの予定

---

### ぜひしたい話
- VSCode Remote Development <!-- .element: class="fragment" data-fragment-index="1" -->
- ngrok <!-- .element: class="fragment" data-fragment-index="2" -->

---

### 時間が余れば
- 色んな辛み <!-- .element: class="fragment" data-fragment-index="1" -->
- ngrokのようなサービス <!-- .element: class="fragment" data-fragment-index="2" -->

---

## ひと昔前のWeb開発あるある

#### 開発中の確認用に本番用やステージング用とは <!-- .element: class="fragment" data-fragment-index="1" -->
### <span class="fragment" style="color: red; font-size: 1.2em; font-weight: bold;" data-fragment-index="2">別のサーバをたてて</span>
### アップロード <!-- .element: class="fragment" data-fragment-index="3" -->

---

## 今にして思えば
### マシン代と電気代 <!-- .element: class="fragment" data-fragment-index="1" -->
### 構築の手間 <!-- .element: class="fragment" data-fragment-index="2" -->
### 複数人で共用してるがゆえの上書きによるデグレの手戻り <!-- .element: class="fragment" data-fragment-index="3" -->

<p style="line-height: 1.2em;"> </p>

## お財布に優しくない <!-- .element: class="fragment" data-fragment-index="4" -->


<aside class="notes">
SubversionやGitで管理してても、Gitが使えない人は何も考えずにファイルを上げる
</aside>

---

## 時代は変わり

### CPUの仮想化支援と多コア多スレッド化 <!-- .element: class="fragment" data-fragment-index="1" -->
### SSDやメモリの大容量化と価格低下 <!-- .element: class="fragment" data-fragment-index="2" -->

<aside class="notes">
仮想化支援機能のついたマルチコアCPU、メモリ8GBぐらいは最低限の人権だと思っています
</aside>

---

## つまり

### てもとのパソコンで仮想環境作っても辛くない <!-- .element: class="fragment" data-fragment-index="2" -->

---

### 仮想化環境下での開発のメリット

<ul>
    <li class="fragment" data-fragment-index="1"><span style="color: red; font-size: 1.2em; font-weight: bold;">秘伝のタレ</span>の防止</li>
    <ul>
        <li class="fragment" data-fragment-index="2">プロビジョニングによるカスタマイズの自動化</li>
        <li class="fragment" data-fragment-index="4">gitで管理してれば<span style="color: red; font-size: 1.2em; font-weight: bold;">どこでも同じ環境を作れる</span></li>
    </ul>
    <li class="fragment" data-fragment-index="6"><span style="color: cyan;">手軽に作れて手軽に壊せる</span>のは初期の試行錯誤には大きなメリット</li>
</ul>

---

### 例

[https://github.com/takwat/vagrant-lamp](https://github.com/takwat/vagrant-lamp)

---

## 個人的に注目の仮想化ソフト
### WSL(Windows Subsystem for Linux)
- 起動が早くWindowsのアプリ感覚でUbuntuが立ち上がるのは楽しい <!-- .element: class="fragment" data-fragment-index="1" -->
- でも現状では結構残念ポイントが多い <!-- .element: class="fragment" data-fragment-index="2" -->
- 次期Windows 10の大規模アップデートでMSが本気を出して作ったLinuxカーネルが登場予定 <!-- .element: class="fragment" data-fragment-index="3" -->
- かなりパフォーマンスが上がって残念ポイントが解決されているらしい <!-- .element: class="fragment" data-fragment-index="4" -->

---

### 仮想環境も解決できない辛み(1)

---

<img src="img/rsync.jpg">

<aside class="notes">
ホスト側とゲスト側で同じ環境を2つも揃えないといけないのが辛い
</aside>

---

### 仮想環境も解決できない辛み(2)

---

<img src="img/vboxsf.jpg">

<aside class="notes">
ホスト側からいじるファイルとゲストから参照するファイルが一元化はされたもののvboxsfの場合は参照が遅い
それでいてホスト環境にもPHPを入れないとだめというのは解決されず
</aside>

---

### VSCode Remote Development Extension

---

<img src="/img/remote.jpg">

<aside class="notes">
- エディタのUI部分だけホスト(Windows/Mac)側で動いてますという形
- 編集対象はゲスト側のローカルファイル
- gitやPHPの実行エンジン(XDebug含む)などはゲスト側で動いているものを使う
- ホスト側にはVirtualBox / Vagrant / VSCode関連以外の開発ツールは一切インストール不要
- 実行・停止の指令と動作状態のモニタリングをサーバ側にインストールされたnode.js製のプラグインなどで行ってホスト側に転送
- SSHぶんのオーバーヘッドはあるもののそこまで気にならない
</aside>

---

## てもとのマシンで開発してたある日

---

## 動いてること見せてもらえない？

---

## どっかにデプロイする？

---

## ぶっちゃけ面倒('A`)

---

## ngrok

---

<img src="/img/ngrok7.jpg">

---

## ただし

<ul>
    <li>有料プランじゃないとすぐ1分あたりのリクエスト数の上限に引っかかる</li>
    <li class="fragment" data-fragment-index="1">画像などのアセットの少ないAPIなどのテスト向きかも</li>
</ul>
