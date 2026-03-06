# my-web-service-kadai
WebサービスをAWSを用い構築

# 今日のインスピレーションボード

AWS AmplifyとGitHubを連携させて構築した、シンプルなWebサービスです。

## 概要
画面を開くと、ランダムな美しい背景画像と、今日の日付、英語のアドバイス（名言）が表示されます。
「新しいインスピレーション」ボタンを押すと、画面をリロードせずに新しい画像と名言を取得します。

## 使用技術
* **フロントエンド**: HTML, CSS, JavaScript
* **ホスティング (CI/CD)**: AWS Amplify
* **バージョン管理**: GitHub
* **使用API**:
  * 背景画像: [Picsum Photos API](https://picsum.photos/)
  * 名言: [Advice Slip API](https://api.adviceslip.com/)

## 構築手順

1. **GitHubリポジトリの作成**
   * GitHubで空のリポジトリを作成。
   * ローカルまたはブラウザから `index.html` をPushする。
2. **AWS Amplifyの設定**
   * AWSマネジメントコンソールから「Amplify」を開く。
   * 「新しいアプリを作成」＞「ウェブアプリをホスト」を選択。
   * ソースコードのプロバイダーとして「GitHub」を選択し、連携を許可する。
3. **リポジトリのデプロイ**
   * このリポジトリと対象のブランチ（`main` または `master`）を選択。
   * 「保存してデプロイ」をクリック。
   * 数分待つと自動でURLが発行され、Webサイトが公開される
