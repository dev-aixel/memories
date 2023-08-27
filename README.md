# <h1><picture>
#   <source media="(prefers-color-scheme: dark)" srcset="./lib/assets/wordmark.dark.png?raw=true">
#   <source media="(prefers-color-scheme: light)" srcset="./lib/assets/wordmark.light.png?raw=true">
#   <img alt="Mastodon" src="./lib/assets/wordmark.light.png?raw=true" height="34">
# </picture></h1>

[![GitHubのリリース](https://img.shields.io/github/release/mastodon/mastodon.svg)][リリース]
[![ビルドステータス](https://img.shields.io/circleci/project/github/mastodon/mastodon.svg)][circleci]
[![コードのクリーンさ](https://img.shields.io/codeclimate/maintainability/mastodon/mastodon.svg)][code_climate]
[![Crowdin](https://d322cqt584bo4o.cloudfront.net/mastodon/localized.svg)][crowdin]

[リリース]: https://github.com/mastodon/mastodon/releases
[circleci]: https://circleci.com/gh/mastodon/mastodon
[code_climate]: https://codeclimate.com/github/mastodon/mastodon
[crowdin]: https://crowdin.com/project/mastodon

Mastodonは、ActivityPubに基づく**無料でオープンソースのソーシャルネットワークサーバー**です。ユーザーはMastodon上で友達をフォローしたり、新しい友達を見つけたりすることができます。Mastodonでは、リンク、画像、テキスト、ビデオなど、何でも投稿することができます。すべてのMastodonサーバーは相互運用可能で、フェデレーションされたネットワークを形成します（1つのサーバー上のユーザーは、別のサーバー上のユーザーとシームレスにコミュニケーションできます。これにはActivityPubを実装した非Mastodonソフトウェアも含まれます！）

以下のリンクをクリックして、動画で詳細を**学ぶ**ことができます:

[![スクリーンショット](https://blog.joinmastodon.org/2018/06/why-activitypub-is-the-future/ezgif-2-60f1b00403.gif)][youtube_demo]

[youtube_demo]: https://www.youtube.com/watch?v=IPSbNdBmWKE

## ナビゲーション

- [プロジェクトホームページ 🐘](https://joinmastodon.org)
- [Patreonを通じて開発をサポートする][patreon]
- [スポンサーを表示する](https://joinmastodon.org/sponsors)
- [ブログ](https://blog.joinmastodon.org)
- [ドキュメント](https://docs.joinmastodon.org)
- [公式Dockerイメージ](https://github.com/mastodon/mastodon/pkgs/container/mastodon)
- [Mastodonサーバーを閲覧する](https://joinmastodon.org/communities)
- [Mastodonアプリを閲覧する](https://joinmastodon.org/apps)

[patreon]: https://www.patreon.com/mastodon

## 特徴

<img src="/app/javascript/images/elephant_ui_working.svg?raw=true" align="right" width="30%" />

### ベンダーロックインなし：準拠するプラットフォームと完全に相互運用可能

Mastodonでなくても、ActivityPubを実装しているものなら、どれでもソーシャルネットワークの一部です！ [詳細を学ぶ](https://blog.joinmastodon.org/2018/06/why-activitypub-is-the-future/)

### リアルタイムの時系列タイムラインの更新

フォローしている人々の更新は、UI上でWebSocketsを介してリアルタイムで表示されます。ファイアホースビューもあります！

### 画像や短いビデオなどのメディアの添付

アップデートに添付された画像やWebM/MP4ビデオをアップロードして表示できます。音声トラックのないビデオはGIFのように扱われ、通常のビデオは連続的にループします！

### 安全性とモデレーションツール

Mastodonには、プライベート投稿、ロックされたアカウント、フレーズフィルタリング、ミュート、ブロックなどの機能が含まれており、報告とモデレーションシステムも備わっています。 [詳細を学ぶ](https://blog.joinmastodon.org/2018/07/cage-the-mastodon/)

### OAuth2と簡単なREST API

MastodonはOAuth2プロバイダーとして機能し、サードパーティのアプリはRESTおよびStreaming APIを使用できます。これにより、多くの選択肢がある豊富なアプリエコシステムが生まれます！

## デプロイメント

### テックスタック：

- **Ruby on Rails** はREST APIおよび他のウェブページを支えています
- **React.js**とReduxはインターフェースのダイナミックパーツに使用されています
- **Node.js**はストリーミングAPIのパワーを提供しています

### 要件：

- **PostgreSQL** 9.5以上
- **Redis** 4以上
- **Ruby** 2.7以上
- **Node.js** 14以上

リポジトリには、**Dockerとdocker-compose**のデプロイメント設定が含まれています。また、**Heroku**、**Scalingo**、および**Nanobox**といった特定のプラットフォーム向けのデプロイメント設定もあります。Helmチャートについては、[mastodon/chartリポジトリ](https://github.com/mastodon/chart)を参照してください。[**スタンドアロン**インストールガイド](https://docs.joinmastodon.org/admin/install/)はドキュメントで利用できます。

開発目的のために**Vagrant**の設定も含まれています。以下の手順を実行して使用できます：

- VagrantとVirtualboxをインストール
- `vagrant-hostsupdater`プラグインをインストール：`vagrant plugin install vagrant-hostsupdater`
- `vagrant up`を実行
- `vagrant ssh -c "cd /vagrant && foreman start"`を実行
- ブラウザで`http://mastodon.local`を開く

## 貢献

Mastodonは**無料のオープンソースソフトウェア**で、**AGPLv3**ライセンスのもとで提供されています。

バグを見つけたり、欠けている機能を提案したりするためにイシューをオープンすることができます。また、このリポジトリにプルリクエストを提出したり、Crowdinを使用して翻訳を提出したりすることもできます。始めるには、[CONTRIBUTING.md](CONTRIBUTING.md)を参照してください。Mastodonに対する貢献が受け入れられると、[OpenCollective](https://opencollective.com/mastodon)を通じて報酬を受け取ることができます。

**IRCチャンネル**: irc.libera.chatの #mastodon

## ライセンス(Mastodon)

著作権（C）2016-2022 Eugen Rochko & その他のMastodonの貢献者（[AUTHORS.md](AUTHORS.md)を参照）

このプログラムはフリーソフトウェアです。あなたはそれを再配布したり、修正したりすることができます。これは、GNU Affero General Public Licenseに基づくものです。ライセンスのバージョンは、Free Software Foundationによって公表されたバージョン3、または（お使いの場合）それ以降のバージョンのいずれかを選択できます。

このプログラムは有用であることを期待して配布されていますが、いかなる保証もなく、暗黙の保証を含め、市販性や特定の目的への適合性に関する保証もありません。詳細については、GNU Affero General Public Licenseを参照してください。

あなたは、このプログラムと共にGNU Affero General Public Licenseのコピーを受け取るはずです。もし受け取っていない場合は、<https://www.gnu.org/licenses/>を参照してください。
