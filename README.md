# Knot - Xposed module for LINE
<p>
  <a href="https://github.com/2b-zipper/Knot/releases/latest"><img src="https://img.shields.io/github/v/release/2b-zipper/Knot?sort=semver&style=flat&label=Release&color=2ea44f" alt="Release"></a>
  <a href="https://github.com/2b-zipper/Knot/releases"><img src="https://img.shields.io/github/downloads/2b-zipper/Knot/total?style=flat&label=Downloads&color=2ea44f" alt="Downloads"></a>
  <a href="https://github.com/2b-zipper/Knot/stargazers"><img src="https://img.shields.io/github/stars/2b-zipper/Knot?style=flat&label=Stars&color=2ea44f" alt="Stars"></a>
  <a href="https://github.com/2b-zipper/Knot/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-GPLv3-2ea44f?style=flat" alt="License"></a>
  <a href="https://crowdin.com/project/knot"><img src="https://img.shields.io/badge/Crowdin-Translate-2ea44f?style=flat" alt="Crowdin"></a>
</p>

![Banner](https://raw.githubusercontent.com/2b-zipper/Knot/main/images/banner.png)

Knotは、Android版LINEのユーザー体験を向上させるために設計された開発中のXposedモジュールです。


> ⚠️このモジュールは個人が学習目的で開発したものであり、LINEヤフー株式会社とは一切関係ありません。本モジュールの使用はLINEの利用規約に抵触する可能性があり、使用に起因するアカウントの制限、凍結、データ消失などのいかなる不利益や損害についても、開発者は一切の責任を負いません。自己責任でご使用ください。

## 対応バージョン・インストール方法

**対応LINEバージョン**と**導入手順**は更新が頻繁なため、こちらには記載していません。必ず元リポジトリの最新の情報を参照してください。

### → [2b-zipper/Knot](https://github.com/2b-zipper/Knot)

| | |
|---|---|
| [対応LINEバージョン](https://github.com/2b-zipper/Knot#readme) | 対応状況はLINEのアップデートに合わせて変わります |
| [Root環境の導入手順](https://github.com/2b-zipper/Knot#root環境) | API 102互換のXposed環境 (Vector等) を使用します |
| [非Root環境の導入手順](https://github.com/2b-zipper/Knot#非root環境) | Fork版NPatch + MicroG-REを使用します。**導入前に必ずトーク履歴をバックアップしてください** |
| [Releases](https://github.com/2b-zipper/Knot/releases) | リリース一覧・変更履歴 |
| [Issues](https://github.com/2b-zipper/Knot/issues) | 不具合報告・機能要望 |

> ⚠️ **このリポジトリには安定版のみを掲載しています。**
> RC版・Beta版などのプレリリースは元リポジトリでのみ公開しています。最新のテスト版を使用したい場合は、元リポジトリの[Releases](https://github.com/2b-zipper/Knot/releases)から入手してください。

<p>
  <a href="https://apps.obtainium.imranr.dev/redirect?r=obtainium://app/%7B%22id%22%3A%22app.zipper.knot%22%2C%22url%22%3A%22https%3A%2F%2Fgithub.com%2F2b-zipper%2Fknot%22%2C%22author%22%3A%222b-zipper%22%2C%22name%22%3A%22Knot%22%2C%22overrideSource%22%3A%22GitHub%22%7D"><img src="https://raw.githubusercontent.com/2b-zipper/Knot/main/images/badge_obtainium.png" height="75" alt="Get it on Obtainium"></a>
  &nbsp;&nbsp;
  <a href="https://github.com/2b-zipper/Knot/releases/latest"><img src="https://raw.githubusercontent.com/2b-zipper/Knot/main/images/badge_github.png" height="75" alt="Get it on GitHub"></a>
</p>

## スクリーンショット

<p float="left">
  <img src="https://raw.githubusercontent.com/2b-zipper/Knot/main/images/sc_settings.png" width="200" />
  <img src="https://raw.githubusercontent.com/2b-zipper/Knot/main/images/sc_plusmenu.png" width="200" />
  <img src="https://raw.githubusercontent.com/2b-zipper/Knot/main/images/sc_talk.png" width="200" />
</p>
<p float="left">
  <img src="https://raw.githubusercontent.com/2b-zipper/Knot/main/images/sc_readhistory.png" width="200" />
  <img src="https://raw.githubusercontent.com/2b-zipper/Knot/main/images/sc_unsend.png" width="200" />
  <img src="https://raw.githubusercontent.com/2b-zipper/Knot/main/images/sc_customfont.png" width="200" />
</p>

## 主な機能

すべての機能の一覧は[knot.2ipper.com](https://knot.2ipper.com/#all-features)にあります。

### プライバシー
- **既読回避**: トークを開いても既読を付けません。「+」メニューでON/OFFでき、送信後やリアクション後に既読を付けることもできます。
- **既読履歴の記録**: 誰がいつメッセージを既読にしたかを記録します。
- **スクロールプレビュー**: LINEラボから削除され、LYPプレミアム限定になったスクロールプレビュー機能を有効化します。
- **従来の長押しメニュー**: トークリストを長押ししたときにプレビューを出さず、メニューだけを表示します。
- **編集履歴の確認**: 編集されたメッセージの編集前のテキストを記録し、長押しメニューから確認できます。
- **トークの完全非表示**: 新しいメッセージを受信しても、非表示にしたトークが再表示されないようにします。
- **送信取り消しの防止**: 相手がメッセージの送信を取り消しても、自分の端末には残るようにします。
- **24時間送信取り消し**: 送信取り消しの時間制限を1時間から24時間に戻します。
- **プロフィールの更新日時表示**: 友だち追加・お気に入り登録・プロフィール更新の日時を、友だちのプロフィール画面から確認できます。

### トーク
- **ミュートメッセージ**: LINEラボから削除され、LYPプレミアム限定になったミュートメッセージ機能を有効化します。
- **高画質写真・長尺動画送信**: 写真を自動圧縮・リサイズせずに最高品質で送り、動画送信の5分の時間制限を解除します。
- **標準カメラ・シャッター音無効化**: LINE内蔵カメラの代わりに端末の標準カメラを使うか、内蔵カメラのシャッター音を無音にできます。
- **トーク内検索の強化**: メンバーでの絞り込み検索と1文字からの検索ができ、検索キーワードアシストを検索バーのボタンで切り替えられます。
- **メッセージの秒数表示**: 各メッセージ横の時刻表示に秒を追加します（例: 12:34 → 12:34:56）。
- **編集モードでの一括全選択**: メッセージ削除画面に、すべてのメッセージを選択・選択解除できるボタンを追加します。
- **リンクをデフォルトブラウザで開く**: URLをアプリ内ブラウザではなく、システムのデフォルトブラウザで開くようにします。
- **AIアイコンの非表示**: メッセージ入力欄のAgent iを、30日間だけでなく永久に非表示にします。

### 表示・UI
- **広告の非表示**: トークリスト上部やホーム画面などに表示される広告を非表示にします。
- **ホーム画面の整理**: ホーム画面のおすすめコンテンツやフィード、サービス一覧を非表示にします。
- **タブのカスタマイズ**: 下部のニュース/通話・アプリ・ショッピング・ウォレットタブを隠せるほか、タブラベルの非表示やタップ範囲の拡大もできます。
- **トークヘッダー・メニューの整理**: トークタブ右上の「AI Friends」「オープンチャット」「カレンダー」「アルバム」ボタンと、各タブの「Agent i」ボタンを非表示にできます。
- **カスタムフォント**: 選択したフォントファイルをアプリ全体に適用します。
- **ピュアブラック (AMOLED) テーマ**: ピュアブラックテーマを適用し、メニューやダイアログも同じ配色に揃えます。
- **サブ端末でのテーマ適用**: サブ端末でログインしたときに、公式設定で非表示になる「着せかえ」項目を表示します。

### 通知・通話
- **リアクション通知**: メッセージについたリアクションを通知します。
- **通知のグループ化・スタック**: 通知を上書きせず、最大7件まで一つの通知の中にまとめて表示します。
- **通知メディアプレビュー**: 画像・動画サムネイル・スタンプ・絵文字をメッセージ通知内にプレビュー表示します。
- **通知から直接既読化**: メッセージ通知に、トークを既読にして通知を消去するボタンを追加します。
- **「通知をオフ」ボタンの非表示**: LINEの通知に表示される「通知をオフ」ボタンを削除します。
- **通知の遅延・不達対策 (FCM Fix)**: 非root環境で通知が届かない問題を回避します（非root環境では既定で有効）。
- **着信音・呼出音のカスタマイズ**: LINE通話の着信音を好きな音声ファイルに差し替えたり、発信時に相手が設定した曲ではなくデフォルトの呼出音を流したりできます。
- **通話録音の通知・アナウンス無効化**: 通話レコーディング時に相手へ送信される録音中通知や画面表示、および録音開始・終了時の音声ガイダンスを無効化します。

## 開発者

- [2b-zipper](https://github.com/2b-zipper)
- [Nich87](https://github.com/Nich87)

## ライセンス

このプロジェクトは[GNU GPLv3](https://github.com/2b-zipper/Knot/blob/main/LICENSE)の下で公開されています。

GPLv3ライセンスに基づき、このプロジェクトのコードのコピー、改変、および再配布は自由ですが、これらを利用・改変したコードを配布する場合は、**ソースコードを公開し、同じGPLv3ライセンスの下で公開する**必要があります。ソースコードを公開せずにコードを無断流用・転載して配布することは禁止されています。
