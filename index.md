# We Love Virtual Machines
仮想環境をより便利に使うツールたち

---

## 自己紹介(1)

<ul>
    <li class="fragment" data-fragment-index="1">0x2c歳</li>
    <li class="fragment" data-fragment-index="2">https://qiita.com/_takwat/</li>
    <li class="fragment" data-fragment-index="3">https://github.com/takwat/</li>
</ul>

---

## 自己紹介(2)
### I Like ...
<ul>
    <li class="fragment" data-fragment-index="1">Slim Framework</li>
    <li class="fragment" data-fragment-index="2">Laravel</li>
    <li class="fragment" data-fragment-index="3">Vue.js</li>
    <li class="fragment" data-fragment-index="4">Vagrant</li>
    <li class="fragment" data-fragment-index="5">Firebase</li>
    <li class="fragment" data-fragment-index="6">MongoDB</li>
    <li class="fragment" data-fragment-index="7">ELK Stack</li>
</ul>

### And ...  <!-- .element: class="fragment" data-fragment-index="7" -->

<h3 class="fragment" data-fragment-index="8"><img src="img/vscode.png" style="width: auto; height: 1em; border: none; vertical-align: middle;">&nbsp;Visual Studio Code</h3>

---

## ここからの予定

### 仮想環境の話 <!-- .element: class="fragment" data-fragment-index="1" -->
### VSCode Remote Development <!-- .element: class="fragment" data-fragment-index="2" -->
### トンネリングサービス <!-- .element: class="fragment" data-fragment-index="3" -->

---

## 開発環境も仮想化の時代

### CPUの仮想化支援と多コア多スレッド化 <!-- .element: class="fragment" data-fragment-index="1" -->
### SSDやメモリの大容量化と価格低下 <!-- .element: class="fragment" data-fragment-index="2" -->
### 人権が守られている開発環境なら仮想マシンを1台ぐらい飼ってもあまり辛くない <!-- .element: class="fragment" data-fragment-index="3" -->

---

### 仮想化環境下での開発のメリット

<ul>
    <li class="fragment" data-fragment-index="1"><span style="color: red; font-size: 1.2em; font-weight: bold;">秘伝のタレ</span>の防止</li>
    <ul>
        <li class="fragment" data-fragment-index="2">プロビジョニングによるカスタマイズの自動化</li>
        <li class="fragment" data-fragment-index="3">↑の設定ファイルはテキストなので、gitなどで管理していれば<span style="color: red; font-size: 1.2em; font-weight: bold;">開発者同士で同じ環境を共有できる</span></li>
    </ul>
    <li class="fragment" data-fragment-index="4"><span style="color: cyan;">手軽に作れて手軽に壊せる</span></li>
</ul>

---

## ただし「銀の弾丸」ではない

---

### 直面する辛み(1)

---

<img src="img/rsync.jpg">

---

### 直面する辛み(2)

---

<img src="img/vboxsf.jpg">

---

## 辛みの根本
### ホスト側とゲスト側とのファイルや環境の整合性の同期
### 二重管理の煩さしさ <!-- .element: class="fragment" data-fragment-index="1" -->

---

# VSCode Remote Development Extension

---

<img src="img/remote.jpg">

<aside class="notes">
- エディタのUI部分だけホスト(Windows/Mac)側で動いてますという形
- 編集対象はゲスト側のローカルファイル
- gitやPHPの実行エンジン(XDebug含む)などはゲスト側で動いているものを使う
- ホスト側にはVirtualBox / Vagrant / VSCode関連以外の開発ツールは一切インストール不要
- 実行・停止の指令と動作状態のモニタリングをサーバ側にインストールされたnode.js製のプラグインなどで行ってホスト側に転送
- SSHぶんのオーバーヘッドはあるもののそこまで気にならない
</aside>

---

# トンネリングサービスの話

---

## てもとの仮想環境で開発してたある日

<img src="https://omoganews.com/wp-content/uploads/2018/08/67476-0-x-1200x630.jpg" width="80%">

---

# &#x1f47c;&nbsp;動いてること見たいなあ

---

# &#x1f641;

---

## どこかにデプロイするの面倒&#x1f630;

---

## APIのコールバックとかだとSSL対応もしないと辛い&#x1f914;

---

## ngrok 降臨

<img src="img/ngrok.png">

---

<img src="img/ngrok7.jpg">

---

## ただし

<ul>
    <li>有料プランじゃないとすぐ1分あたりのリクエスト数の上限に引っかかる&#x1f631;</li>
    <li class="fragment" data-fragment-index="1">APIなどのテスト向きかも</li>
    <li class="fragment" data-fragment-index="2">Vagrantにあるshareというプラグインも裏側でこれ使ってます</li>
</ul>

---

## 似たようなサービス

---

### serveo

https://serveo.net/

---

<ul>
    <li>サービスがたまに落ちてる&#x1f607;</li>
    <li class="fragment" data-fragment-index="1"><span style="font-weight: bold; font-size: 1.2em; color: cyan;">自鯖・自ドメインで環境作れる</span></li>
    <li class="fragment" data-fragment-index="2"><span style="font-weight: bold; font-size: 1.2em; color: cyan;">ただのトンネルなのでどこかの安鯖にたててもいいかもしれない</span></li>
</ul>

---

### Localtunnel

https://localtunnel.github.io/www/

---

<ul>
    <li>npm installなのでクライアントのインストールが楽</li>
    <li class="fragment" data-fragment-index="1"><span style="font-weight: bold; font-size: 1.2em; color: cyan;">自鯖・自ドメインで環境作れる</span></li>
    <li class="fragment" data-fragment-index="2">若干パフォーマンスが不安</li>
</ul>

---

## まとめ

<ul>
    <li class="fragment" data-fragment-index="1">開発環境と普段使いの環境の隔離</li>
    <li class="fragment" data-fragment-index="2">VSCode使いならRemote Developmentは入れといたほうが幸せ</li>
    <li class="fragment" data-fragment-index="3">簡易的ではあるものの仮想環境をグローバルに晒す手段もあるので用法容量をよく守ってお使いください</li>
</ul>

---

# 本題終わり

---

## 余談

---

### KEN_ALL.csvの闇は深い

https://qiita.com/_takwat/items/3a121656425fac7bb820

---

# ありがとうございました
#### 資料
https://takwat.github.io/tagayas/
