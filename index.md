---
id: dist
{{if .Meta.Status}}status: {{.Meta.Status}}{{end}}
{{if .Meta.Summary}}summary: {{.Meta.Summary}}{{end}}
{{if .Meta.Author}}author: {{.Meta.Author}}{{end}}
{{if .Meta.Categories}}categories: {{commaSep .Meta.Categories}}{{end}}
{{if .Meta.Tags}}tags: {{commaSep .Meta.Tags}}{{end}}
{{if .Meta.Feedback}}feedback link: {{.Meta.Feedback}}{{end}}
{{if .Meta.GA}}analytics account: {{.Meta.GA}}{{end}}

---
# Voiceflowハンズオン＆ワークショップ：インタラクティブな物語スキルを作ろう

## 概要

### はじめに

![story01-001](images/vf-handson-story-top-logo.png)

本資料は、「Voiceflowハンズオン＆ワークショップ：インタラクティブな物語スキルを作ろう」のハンズオン用資料になります。

アカウントのセットアップなど事前準備は以下をご覧ください。

- Voiceflowハンズオン: アカウントのセットアップ手順
[https://vf-handson-setup.netlify.com/#0](https://vf-handson-setup.netlify.com/#0) 

### 注意

Negative
: 本手順書は2019年11月21日時点のものですが、Voiceflowの開発はかなり活発なので、本手順書通りに進めてもうまくいかない場合や画面が変更されている場合があります。ご容赦ください。（必要な場合は補足します）

Positive
: 不具合やお気づきの点があれば、[https://github.com/kun432/voiceflow-handson-story/issues](https://github.com/kun432/voiceflow-handson-story/issues)でissue立てていただければと思います。PRも歓迎！

Positive
: 不具合やお気づきの点があれば、kun432.8d1w@gmail.comまで。

### 更新履歴

- 2019/11/21    公開

ではNextをクリックしてください

## プロジェクトの作成と基本操作

### プロジェクトの作成

最初にプロジェクトを作成して、かんたんにVoiceflowの画面の説明を行います。

以下のURLにアクセスしてください。
[https://voiceflow.com/](https://voiceflow.com/)

右上の"Log in"をクリック。

![story02-001](images/story02-001.png)

アカウント作成した際のメールアドレスとパスワードを入力して"Sign in"をクリックします。

![story02-002](images/story02-002.png)

プロジェクトの一覧画面が表示されます。Default Listと書いてあるところの一番下の"Create Project"をクリックします。

![story02-003](images/story02-003.png)

プロジェクト作成画面が開きますので、以下の通り設定して、最後に"Create Project"をクリックします。

- プロジェクト名
  - 今回は「世界の音絵本」と入力してください。
  - スキルを呼び出すときのデフォルトの名前になります。（例：「アレクサ、◯◯◯を開いて」）
  - 後でプロジェクト名と呼び出し名のそれぞれを変更することも可能です。

- 言語: "English(US)"のチェックを外して、"Japanese(JP)"にチェック

![story02-004](images/story02-004.png)

プロジェクトが作成されると"Canvas"画面が表示されます。"Canvas"画面がVoiceflowでスキルを作成する基本画面になります。

- 最初から用意してあるHome Blockの中にあるStartがスタート地点になります。
- 左のBlocksメニューにいろんな機能のBlockが用意されています。ここからBlockを選択してCANVAS上に配置します。
- CANVASに配置したBlockの設定を行い、アレクサに発話させたり、ユーザの発話を受け取ったりします。
- Block同士を線でつなげることで、会話の流れがつながっていきます。
- アップロードボタンをクリックすると、作成したプロジェクトがAlexa開発者コンソールにアップロードされ、Amazon Echoなどで呼び出せるようになります。
- Blocksメニュー以外にもいくつか別のメニューがありますが、後で説明します。

![story02-005](images/story02-005.png)

では早速やってみましょう。

### CANVASとBlockの使い方

Voiceflowでは、いろんな機能を持ったBlockをCanvasに配置して線をつなぐことで、会話の流れを作ることになります。試しに少しやってみましょう。

左のBlocksメニューの一番上にある"Speak"というブロックを、最初から配置してあるHome Blockの右側あたりにドラッグ＆ドロップで配置してください。すると、画面の右側に別の設定画面が出てくると思います。

![story02-006](images/story02-006.png)

この設定画面の右上の入力欄に以下と入力してみてください。

```
世界の音絵本にようこそ。このスキルでは、世界の有名な童話を楽しくお話します。
```

![story02-007](images/story02-007.png)

そして、Home BlockのStartの右端からSpeak Blockの左端までドラッグしながら線でつなげます。

![story02-008](images/story02-008.png)

はい、これが基本的な操作になります。かんたんですよね？おさらいでもう一つSpeak Blockをつなげてみましょう。

- 最初に配置したSpeak Blockの右側にもう一つSpeak Blockを配置します。
- Speak Blockの設定画面の入力欄に以下を入力します
```桃太郎、シンデレラ、ガリバーの冒険、のどれを聞きたいですか？```
- Speak Block同士を線でつなげます。

![story02-009](images/story02-009.png)

２回目なのでもう大丈夫ですよね。ちなみに、線を引き直したい場合は、線の始点側のブロックの四角をクリックするか、線の真ん中にカーソルを合わせると表示されるバケツアイコンをクリックすると消せます。

![story02-009_2](images/story02-009_2.png)

では作ったスキルを実際に動かしてみたいと思います。

### スキルのアップロードとテスト

作成したスキルを動かすにはAlexa開発者コンソールへのアップロードが必要です。右上の"Upload to Alexa"というボタンをクリックしてください。

![story02-010](images/story02-010.png)

初回に限り、VoiceflowアカウントとAlexa開発者アカウントの紐付けが必要になります。"Connect Amazon"ボタンをクリックしてください。

![story02-011](images/story02-011.png)

Amazonアカウントのログイン画面が出てきますので、お持ちのAmazonアカウントでログインします。

![story02-012](images/story02-012.png)

VoiceflowからAmazonアカウント経由でAlexaスキル作成等の許可を求める画面が出てきますので、「許可」をクリックします。これでアカウントの紐付けは完了です。

![story02-013](images/story02-013.png)

アップロードが行われます。100%になるまで待ちます。

![story02-014](images/story02-014.png)

100％になって"Upload Successful"と表示されればアップロード完了です。ではAlexa開発者コンソールでテストしましょう。"Test on Alexa Simulator"をクリックしてください。

![story02-015](images/story02-015.png)

Alexa開発者コンソールのログイン画面が表示されたら、Amazonアカウントでログインしてください。

![story02-016](images/story02-016.png)

Alexa開発者コンソールのテストシミュレータ画面が表示されます。作成したスキルはここでほぼ実機と同じようにテストができます。

![story02-017](images/story02-017.png)

なお、この時、左上のところで「非公開」が選択されていた場合は「開発中」に変更します。

![story02-019](images/story02-019.png)

テストは文字だけでなく音声でも行なえます。まず最初にマイクを有効にしておきましょう。「許可」をクリックします。

![story02-018](images/story02-018.png)

ではいよいよテストです。「日本語」が選択されていることを確認して、マイクアイコンをクリックしたままマイクに「音絵本を開いて」と話しかけて、話し終わったら話してみてください。パソコンにマイクがない場合は、キーボードから入力してENTERキーを押してください。

![story02-020](images/story02-020.png)

あなたの発話に対して、Voiceflowで設定した内容をAlexaが返してくれればテストは成功です！これでスキル開発の第一歩を踏み出したことになります！おめでとうございます！

![story02-021](images/story02-021.png)

このように、Voiceflowでスキルを作成 → Alexa開発者コンソールにアップロード → Alexa開発者コンソールでテスト、というのがVoiceflowでのスキル開発の流れになります。どうでしょうか？そんなに難しくないですよね？この調子で続けていきましょう！

"Next"をクリックしてください

## いろいろなブロック

ここで少し最初に使ったブロックの説明をしながら、他のブロックもご紹介します。

### Speak Block

最初に使ったSpeak Blockは、皆さんもうおわかりのように「アレクサがしゃべる」ブロックになります。

![story02-007](images/story02-007.png)

"Speaking as"の横のリストを変更すると、他の声に変更することができます。日本語はアレクサの他に、"Mizuki"（女性）、"Takumi"（男性）の声を選ぶことができます。物語に複数のキャラクターが出てくる場合などに活用できそうですね！

![story02-022](images/story02-022.png)

Positive
: ちなみに外国人の声を選ぶとカタコトの日本語みたいになって面白いです。外国人が日本に来た、みたいなシチュエーションで使うのも面白いかもしれません。

Negative
: ただし、外国人の声を選んだ場合、日本語を正しく発音してくれるかどうかは保証されません。今回は説明しませんが、外国人の声で外国語を話させる場合にはSSMLというタグを使って、どの言語を話すか？をきちんと指定するのが本来のやり方になります。

その他、Speak Blockでは、サウンドを再生させることもできますが、それは後で説明します。

### Interaction Block

アレクサにしゃべらせることができたら、次は、ユーザがしゃべったことを受け取ってみるのにチャレンジしましょう。ユーザの発話を受け取るブロックは複数ありますが、もっとも活用の幅が広いInteraction Blockを使ってみましょう。

Blocksメニューの下の方にAdvancedというサブメニューの中ににある Interaction Block を、2つ目のSpeak Blockの右側にドラッグアンドドロップして、線でつなげてください。

![story02-023](images/story02-023.png)

Speak Blockのときと同じようにInteraction Blockの設定画面も表示されましたよね。Interaction Blockの設定画面に3つのタブがあるのがわかるでしょうか？

![story02-024](images/story02-024.png)

それぞれのタブで設定する内容は以下となります。

- Choices
  - Intentsで設定したインテントに基づいて、会話の流れを分岐させます。

- Intents
  - ユーザのしゃべりそうな内容のパターン（「サンプル発話」と言います）をグループ（「インテント」と言います）にまとめることで、分岐の元となるルールを作ります。

- Slots
  - ユーザのしゃべる内容の中に含まれるキーワードを変数として、スキルからプログラム的に利用する場合に使用します。（今回は使用しません）

といっても、いきなりではピンとこないですよねー。では実際に設定してみましょう！

Intentsタブをクリックして、"Add Intent"をクリックしてください。

![story02-025](images/story02-025.png)

下に”intent_one"という設定が追加されたと思います。"intent_one"がインテント名になります。まずここで、"intent_one"というのをわかりやすく"momotaro_intent"に変えてください。

![story02-026](images/story02-026.png)

入力欄に「桃太郎」と入力してENTERキーを押します。入力欄の下に表示されればOKです！

![story02-027](images/story02-027.png)

同様にして、以下のように入力してみてください。

![story02-028](images/story02-028.png)

これで1つ目のインテントの登録が完了しました。これを繰り返して、"cinderella_intent"と"gulliver_intent"を作ります。ここは説明を省略します。下にコピペ用のテキストを用意してみたので、トライしてみてください！

- cinderella_intent

```
シンデレラ
シンデレラが聞きたい
シンデレラを聞かせて
シンデレラがいいな
シンデレラをお願い
```

- gulliver_intent 

```
ガリバーの冒険
ガリバーの冒険が聞きたい
ガリバーの冒険を聞かせて
ガリバーの冒険がいいな
ガリバーの冒険をお願い
```

全部入力し終わってこんな感じになっていればOKです！

![story02-029](images/story02-029.png)

では、次にこのインテントを使って分岐をしてみましょう。Choicesタブをクリックして、"Add Choice"をクリックしてください。

![story02-030](images/story02-030.png)

すると下に設定項目のようなものが追加されるとともに、Interaction Blockにも線をつなぐための四角が追加されて、同じ番号になっているのがわかるでしょうか？

![story02-031](images/story02-031.png)

同じように"Add Choice"をあと2回クリックしてみてください。さらに2つの設定項目と、Block側にも2つの四角が追加されます。

![story02-032](images/story02-032.png)

では設定項目の"Select Intent"をクリックしてみてください。先程作成した３つのインテントが並んでいるのがみえますよね？

![story02-033](images/story02-033.png)

それ以外にも色々表示されていますが、そこはちょっと置いといて。3つのインテントをそれぞれ以下のように選択してみてください。

![story02-033](images/story02-034.png)
