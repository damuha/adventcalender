# Notion Blogでブログを開設しました
ちょっと前になりますが、[Notion Blog](https://notion-blog.vercel.app/)でsisterのブログを開設したので、開設するまでの流れを書いてみようと思います。

▼sisterのブログはこちらです↓
https://blog.sisterwith.com/

▼ Notion Blogはこちらです↓
https://notion-blog.vercel.app/

▼ 参考記事はこちらです↓
https://blog.35d.jp/2020-05-23-notion-blog-1

## Notion Blogとは
Notion Blog とは、Notion（バックエンド）で作成したブログ記事を Next.jsで作られたプロジェクト(フロントエンド)でWeb上に公開できるヘッドレスCMS（コンテンツマネジメントシステム） です。

## 環境
・Vercel
・Notion　Blog（Next.js、TypeScrypt）
・Notion

## 1, Notion BlogをVercelにデプロイする

### ①Deployボタンをクリック
[Notion Blog](https://notion-blog.vercel.app/)にアクセスし、以下のDeployボタンをクリックする

![](https://storage.googleapis.com/zenn-user-upload/7f32bc18c2ffa53695121b8b.png)

### ②GitHubと連携

GitHubのボタンからGitHubと連携します
![](https://storage.googleapis.com/zenn-user-upload/480c9894876e37694a85845d.png)

<br>
対象のGitHubアカウントとプロジェクト名を入力して、Continueボタンをクリックします
![](https://storage.googleapis.com/zenn-user-upload/eeac06c77d997c7dd3fe7fe2.png)
<br>
対象のGitHubとリポジトリ名を入力して、Continueボタンをクリックします
![](https://storage.googleapis.com/zenn-user-upload/21159e3897c8e6f075d3ce55.png)

### ③プロジェクトのデプロイ準備

プロジェクト名は特に変更しないで、進めます。
FRAMEWORK PRESETはNext.jsにします（デフォルトでなってるはず）
![](https://storage.googleapis.com/zenn-user-upload/000ce3aa57acc02af75d5c5a.png)
<br>
自分のNotionとBlogを連携させるために、環境変数を設定します
**・NOTION_TOKEN
・BLOG_INDEX_ID**
![](https://storage.googleapis.com/zenn-user-upload/bc5a0c35737f3fe7a596f0bf.png)

#### NotionでNotion Blogと連携させたいページを作成する
事前にNotionでNotion Blogと連携させたいページを作成する必要があります。
※ここでは一旦ページだけの作成で大丈夫です
![](https://storage.googleapis.com/zenn-user-upload/e0bca67d23febaba887f4738.png)

#### NOTION_TOKEN取得方法

開発ツールの以下箇所がNOTION TOKENです
Applicationタブ ＞ Storage ＞ Cookies ＞ https://www.notion.so 
Name: token_v2のValue

![](https://storage.googleapis.com/zenn-user-upload/7360c6c9053abaff7b5cb059.png)
<br>
#### BLOG_INDEX_ID取得方法
NotionでNotion Blogと連携させたいページのURLの以下XXXXの箇所が**BLOG INDEX ID**です。
https://www.notion.so/Notion-Blog-XXXXXXX
![](https://storage.googleapis.com/zenn-user-upload/7360c6c9053abaff7b5cb059.png)
<br>
#### 上記で取得した環境変数をVercelで設定します

![](https://storage.googleapis.com/zenn-user-upload/251670460c7c7b4d63213351.png)

### ④プロジェクトをインポート＆デプロイする
デプロイ準備が完了したら、Deployボタンをクリックして、プロジェクトをデプロイします。

![](https://storage.googleapis.com/zenn-user-upload/1f400463ce1f701824726762.png)
<br>
〜〜デプロイ中〜〜
![](https://storage.googleapis.com/zenn-user-upload/d5308bb9aabb1cc9c9c35abe.png)
<br>
デプロイ完了！！あっという間だ〜
![](https://storage.googleapis.com/zenn-user-upload/70e87c0f504512bdaaf5e47f.png)

### ⑤ちゃんとデプロイできているか見に行く
My Notion Blogの画面が表示されていれば、デプロイ成功！！
![](https://storage.googleapis.com/zenn-user-upload/5ff378195d0cb69311a2456d.png)
<br>
Blogはまだ投稿されていないので、空っぽですね。
![](https://storage.googleapis.com/zenn-user-upload/499b8b551c9ac1bd7cfbe769.png)

## 2, ブログを投稿する
### インラインテーブル[^1]を作成する

テーブル名は「Index」とします。
![](https://storage.googleapis.com/zenn-user-upload/646b738442eb27d0cb3c15dc.png)
<br>
### テーブルカラムを作成する
テーブルのカラムですが、[こちら](https://github.com/ijjk/notion-blog)でRead Meにも記載されているとおり、指定されたカラムがないと認識されないようなので、ReadMeの通り作成します。または、テーブルを作成するスクリプトを用意してくれているので、そちらを使用しても大丈夫です。

Page: ページタイトルと内容
Slug: ブログページのURL/blog/xxxのxxxの部分です。Text形式。
Published: 公開/非公開設定です。Checkbox形式
Date: ブログ作成日です。Date形式
Authors: ブログ作成者です。Person形式

![](https://storage.googleapis.com/zenn-user-upload/3b6057634905ad76be045046.png)
<br>
[^1]: Notionでのインラインテーブルの説明はこちらの記事がわかりやすかったです。
https://note.com/mamizo/n/nade3aba29ab6

### 記事を作成する

適当に記事を作成します。
![](https://storage.googleapis.com/zenn-user-upload/646b738442eb27d0cb3c15dc.png)

![](https://storage.googleapis.com/zenn-user-upload/462d3577e59966da35a76e9f.png)

### ブログが投稿されているか確認する
ブログが投稿されたか確認します。
反映されていますね！！
![](https://storage.googleapis.com/zenn-user-upload/9ce72e023f797338a184bcba.png)
![](https://storage.googleapis.com/zenn-user-upload/992546da9fc88148b8e3f702.png)

一旦、ブログの構築は完了です！！
10分くらいで構築できちゃうと思います！！簡単だ〜

ただ、カスタマイズしたいですよね、、ローカルで触りたいですよね！！
ここからは、ローカル環境構築手順について書いていきます〜

## 3, DockerでNotion Blogのローカル環境を構築する
事前に先ほどGitHubにあげたnotion-blogリポジトリをcloneしてきてください！

また、ローカル環境はDockerじゃなくても問題ありません。私個人的に、MacBookを汚したくない精神が強いため、開発環境を構築する際は毎回、Dockerを使用しているので、今回もDockerで環境構築しました！！

### ①Dockerfileを作成する
Dockerfileを作成します。
私はyarnも一緒にインストールするところまで、書いてますが、どっちでもいいかなと思います。

```
FROM node:14.15.3
WORKDIR /usr/src/app

RUN curl https://deb.nodesource.com/setup_12.x | bash
RUN curl https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update && apt-get install -y yarn
RUN apt install direnv

RUN yarn install
```
※こっちのコマンドでもyarn installできます！
```
% docker-compose run node yarn install
```

### ②docker-compose.ymlを作成する
docker-compose.ymlを作成します。

```yml
version: '3'
services:
  node:
    build:
      context: .
      dockerfile: Dockerfile
    volumes:
      - .:/usr/src/app
    command: sh -c "yarn dev"
    ports:
      - "3000:3000"
```


※ディレクトリ構成はこんな感じです
![](https://storage.googleapis.com/zenn-user-upload/6d44728710305b3402c1510b.png)

### ③docker-compose　up -dでコンテナを起動する

```
damuha@otion-blog % docker-compose up -d
Docker Compose is now in the Docker CLI, try `docker compose up`

Starting notion-blog_node_1 ... done
damuha@notion-blog % 
```

### ④http://localhost:3000で確認する

http://localhost:3000 にアクセスして、ローカル環境がうまく構築できたか確認します。
できてますね！！
![](https://storage.googleapis.com/zenn-user-upload/d799d3c0d586562cd5481501.png)

### ⑤Notionと連携する
ローカル環境でも以下の環境変数を設定します。
私は本番と同じNotionページを設定しています。
**・NOTION_TOKEN
・BLOG_INDEX_ID**

ローカル環境では　**.env**　に設定します。
```.env
BLOG_INDEX_ID=xxxxxxxxxxxx
NOTION_TOKEN=xxxxxxxxx
```
<br>
ローカル環境でもNotionのブログ記事が表示されていることを確認できました！！
![](https://storage.googleapis.com/zenn-user-upload/590136187e53554034fd2d7b.png)
![](https://storage.googleapis.com/zenn-user-upload/9a66d3b0fa241fbdc9f43954.png)

## 4, いろいろカスタマイズして自分だけのブログを作ってみよう！！
はい、こんな感じで、ブログを開設することができました！
sisterのブログはもっと色々とカスタマイズしています。
https://blog.sisterwith.com/

- 全体的なスタイルを変えたり、
- タグごとに記事を表示できるようにしたり
- アイコン画像を入れたり

![](https://storage.googleapis.com/zenn-user-upload/de731d49f9fb492223baccc5.png)

## （おまけ）作ってみた私の感想!!
自分の好きなようにフルカスタマイズできるので、めちゃくちゃNext.jsの勉強にもなるんじゃないかな〜とカスタマイズしてて思いました！！私は、Next.jsは初めて触ったのですが、基礎的な部分の
・APIでデータ取得してくる
・ルーティング
・コンポーネント連携
などは枠組みが用意されているので、すごく勉強になりました。

ただ、あくまで、エンジニア向けで、エンジニア以外の方には結構ハードルが高いかなと思います！！WordPressのようにデザインのテンプレートが用意されていたり、プラグインがあったりするわけではないです。

また、Anotionという誰でも簡単にNotionでブログを構築できるサービスもあるようなので、ぜひチェックしてみてください〜！
https://anotion.so/

## 最後に

長い記事を最後まで読んでいただきありがとうございました！！
次回は独自ドメインの適用部分もかければいいなと思います！！


