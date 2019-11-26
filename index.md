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

２回目なのでもう大丈夫ですよね。ではここで作ったスキルを実際に動かしてみたいと思います。

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



