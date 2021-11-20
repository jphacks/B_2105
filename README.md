# Tech.面接


![Tayzer](https://user-images.githubusercontent.com/63713624/139520215-b30afad8-357e-498e-afb4-424b8eb3651e.png)

## 製品概要
### 背景(製品開発のきっかけ、課題等）
#### 我々23卒世代が特に今年頭を抱えたリモート面接の対策に課題はありました。リモート面接の対策なんてどうしたらいいのだろうか。相手にどんなふうに表情が伝わっているのか、友達と練習するにもリモートだとなあ。。時間を撮ってもらうのも申し訳ないし。。そういった悩みを課題点として考えました。

### Demo Video
https://youtu.be/iM4eFFg3s1M

### 製品説明（具体的な製品の説明）
#### リモート面接の不安を解消してくれるwebアプリケーションです。Github/Googleアカウントよりアカウントを作っていただき、「模擬面接モード」「練習モード」二つのモードがあり、「模擬面接モード」では本番の面接と近い３０分間の面接、「練習モード」では時間がない方向けにランダムに面接によく出る問題が画面に表示されます。ユーザーはリモート面接受けているような雰囲気で喋って終了したらその喋った動画をAIが分析して注意する部分を指摘してくれます。


### 特長

#### 1. FaceAPIによる感情データ分析
#### 2. 重回帰分析を用いた独自で開発した印象分析モデル
#### 3. それらの数値をChart.jsによりグラフ化

### 今後の展望
* 学生エンジニアの7割がこのwebサービスを通して練習する
* サンプルを集めて印象データの精度を高める
* 自然言語処理により面接受ける人は話したいことをまとめることができているのかフィードバックと改善点を指摘
* 顔の位置や動画の明るさを感性情報に基づき、よりいい印象を出す方法を教えてくれる

### 注力したこと（こだわり等）
* 自作AIモデルによるデータ分析
* Cloud run によるコンテナ インスタンスが必要に応じてスケーリングされ、ユーザーが多い場合でも応答時間が短くなるように最適化


## 開発技術

### アーキテクチャー
<img width="412" alt="image" src="https://user-images.githubusercontent.com/80163799/142715585-7b319e2f-1616-4e1f-916d-e7c2c4b21c56.png">

### 活用した技術
#### API・データ
* Microsoft Azure Face API
* 画像に対しての印象アンケートデータ

#### フレームワーク・ライブラリ・モジュール
* FastAPI
* OpenCV

#### インフラ・開発ツール
* Google Cloud Platform (CloudRun)
* Github Actions for auto deploying to CloudRun


### 独自技術
#### 印象予測機能
* Face API を活用して画像から感情のデータを獲得した。そして、「誠実そう」、「自信ある」、「リーダーシップありそう」、「一緒に働きたい」、「緊張しているように見える」、「不安そうに見える」とiいったアンケートからの印象データを目的変数とし、重回帰分析を行うことで、感情データから印象を予測できるモデルを作成した。

<img width="644" alt="Screen Shot 2021-11-20 at 9 31 33" src="https://user-images.githubusercontent.com/78252529/142713352-203ec54b-1e4f-47f5-941d-c516c473e41c.png">
