# 今日のインスピレーションボード

**🌐 ライブデモ（実際の画面）はこちら:** [Webサービスを開く](https://main.xxxx.amplifyapp.com)

AWS AmplifyとGitHubを連携させて構築した、シンプルなWebサービスです。

## 概要
画面を開くと、ランダムな美しい背景画像とともに、今日の日付、現在の気温（東京）、そして日本語の名言が表示されます。
「新しいインスピレーション」ボタンを押すと、画面をリロードせずに新しい画像と名言を切り替えます。

## 使用技術
* **フロントエンド**: HTML, CSS, JavaScript
* **ホスティング (CI/CD)**: AWS Amplify
* **バージョン管理**: GitHub
* **使用データ・API**:
  * 背景画像: [Picsum Photos API](https://picsum.photos/)
  * 天気情報: [Open-Meteo API](https://open-meteo.com/) (登録不要の無料API)
  * 名言: JavaScriptの配列（リスト）を使って独自の語録を管理

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
  
   ## 🧠 今回の開発で難しかった・工夫したコード

初めてのWebサービス開発で、特に理解が難しかった部分のメモです。

### 1. 外部APIからのデータ取得（非同期処理）
```javascript
async function loadWeather() {
    try {
        const res = await fetch('[https://api.open-meteo.com/v1/forecast](https://api.open-meteo.com/v1/forecast)?...');
        const data = await res.json();
        const temp = data.current_weather.temperature;
        // 画面に表示する処理...
    } catch (error) {
        // エラー時の処理...
    }
}

// meigenListは名言がたくさん入った配列（リスト）
const randomIndex = Math.floor(Math.random() * meigenList.length);
document.getElementById('quote').innerText = meigenList[randomIndex];

### ステップ3：保存（Commit）する
貼り付けたら、画面右上の緑色の **「Commit changes...」** を押し、再度 **「Commit changes」** を押して上書き保存します。

---
マークダウンのコードブロック（````javascript` と ```` で囲む記法）を使うことで、**README上に本物のエディタのように色付きでプログラミングコードが表示される**ようになります。
