# インターン参加経験
- brainpad
  - 2022年8月1日ー2022年8月5日
- yahoo
  - 8月下旬2週間
- DeNAハッカソン
  - 9月中旬
- (予定)
  - 3日間
  
# 過去経歴・作品紹介
- 2019年夏: スクレイピングシステムの開発
  - ソースコード
    - なし
  - 概要
    - 初めて授業以外でプログラミングに触れ、なんとか動くところまで開発できたプログラム。
    - webサイトから情報をスクレイピングし、自動的にブログにアップロードするシステムを、約一ヶ月かけ開発、その後1年半ほど改良を続けました。
  - 技術
    python, aws lambda, step functions, s3, wordpress REST API, twitter API
    - スクレイピング
      - 言語は python を使用
      - 静的サイトに対しては、requests ライブラリでソースを取得、lxml ライブラリで要素を抜き出し
      - 動的サイトに対しては、selenium ライブラリを使用しブラウザを操作、要素を抜き出し
    - ブログにアップロード
      - ブログは、ロリポップというレンタルサーバー上にwordpressで構築
      - wordpress REST API を利用してpythonからPOSTメソッドを叩くことで、自動投稿を実現
      - 記事の投稿をTwitter上て通知するプログラムの作成
    - 定期実行: 
      - aws lambda, step functions を利用
      - aws lambda の「一回の実行が15分まで」という制限を克服するため、step functions を利用して関数を再帰的に呼び出す必要があった
      - step functions と aws lambda で構築された１連のプログラムを、cron で定期実行
    - 苦労したこと
      - 初めての大規模な開発だったので、ソースコードを管理することが大変でした。github も知らなかったため、ソースコードを修正するたびにファイル名に日付を書いてコピーを保存していました。
      - aws lambda で selenium ライブラリを利用することにも苦労しました。selenium ライブラリを利用するために、chrome driver などのウェブドライバを利用するのですが、これを lambda 上で認識させるのに何日もかかった記憶があります。
      - また、lambda 上にソースコードをアップロードする方法も非効率極まりないものでした。現在ならば Layer にライブラリをまとめて使い回すことができますが、当時はその方法を知らず、全てのソースコードと依存するライブラリを全て zip にまとめてインポートしていました。　ソースコードを修正するたびに、50MB以上もあるフォルダの zip 化とアップロードの作業を挟まなければならず、非常に無駄の多い開発になっていました。
- 2019年秋~2021年: サービス立ち上げ、システム開発のお手伝い
  - ソースコード
    - 非公開
  - 概要
    - ウェブサービスの立ち上げをお手伝いしました（具体的には、web上の情報などを用いてお店の宣伝を行うツイッターアカウント、ブログを運用）。
    - また、サービスに利用するシステムを社会人のプログラマーの方と2人で開発を行いました。
    - スクレイピング、DB上のデータを表示するWebページの作成、記事の自動投稿などを行いました。
    - github によるコードの共有、可読性を考えたコードの書き方、オブジェクト指向開発などを学びました。
  - 技術
    PHP, laravel, docker, mysql, wordpress REST API, twitter API, github, javascript
    - スクレイピング
      - 言語は PHP を使用
      - オブジェクト指向で書かれた他人の書いたコードを利用し、関数の追加やクラスの追加を行い、機能を拡張した
    - DB 上のデータを表示するwebページの作成
      - DB は mySQL、PHPフレームワークの laravel を使用
      - laravel の Eloquent という機能を用いて PHP で DB を操作
      - DB から取り出したデータを用いて、HTMLを生成、javascript を用いたグラフの描画も行なった
  - 苦労したこと
    - docker というものを初めて使い、docker インストールから、ビルドやコンテナ間の通信まで、何から何まで苦労しました。docker を動かすためにwindows10 を home から pro に変更したり、.env ファイルを埋めなければならない事を初めて知ったり、 環境構築に泣かされました。
    - 他人のコードを読んで、それを利用するという行為を初めて行いましたが、コードを読む時間の方が書いている時間よりも長くて驚きました。しかし、人のコードを読むと学びが多く（変数や関数を punlic にするか private にするかの基準や、デザインパターンの使い所など）、大変有意義な時間でした。
- 2021年春: アプリ「ウマ娘」のフレンド募集サイト開発
  - ソースコード
    - [uma-friend](https://github.com/nntto/uma-friend)
  - サイト
    - [https://uma-friend.web.app/](https://uma-friend.web.app/)
  - 概要
    - [りあクト！](https://oukayuka.booth.pm/items/2368045)という本と出会い、web制作に興味を持ち始めた
    - javascript も授業以外では触ったことがなかったが、この本のおかげで、javascript・typescript・react を使うことができた
    - スマホアプリ「ウマ娘」のフレンドを募集する掲示板を作成した
  - 技術
    typescript, react, firebase
    - フロントエンド
      - react で作成
      - ゲーム内のデザインにできるだけ近づけるよう意識した
    - バックエンド
      - typescript を使用
      - データベースとして、Firestore Database と Google spread sheet を使用
        - Google spread sheet を使用した理由は、頻繁に追加更新されるゲーム内のキャラクターやスキルなどをどこからでも更新できるようにするため
  - 苦労したこと
    - 環境構築に一番時間がかかっています
      - typescript を利用するために vscode に eslint, prettier を導入しましたが、警告が表示されなかったり、自動整形が走らなかったり、とても苦労しました。
    - Webブラウザとデータベースの通信に非常に苦労しました。
      - firebase　のアクセスルールや、　GCP　の権限、 CORS の設定など、アクセス権限の設定に大きく時間を取られました。
      - form に入力されたデータを取得し、送信する機構を作成することも難しかったです。
    - フロントエンドのデザインには非常に苦労しました。
      - css を設定して、ダイヤマークや星マークをデザインしたり、オブジェクト同士の間隔を揃えたり、非常に難しかったです。
      - レスポンシブデザインを採用し、画面幅によってレイアウトが動的に決定されるようにすることにも時間がかかっています。
- 2021年夏~現在: ライトノベル推薦サイトの開発
  - ソースコード
    - 非公開
  - 概要
    - 作品に対するレビューから特徴量を抽出し、近い特徴をもつ作品を推薦するサイト
    - 鋭意製作中
  - 技術
    - フロントエンド: react, typescript
    - バックエンド: PHP, laravel, python
    - DB: mysql
  - 苦労した点
    - 知人と二人で開発しているのですが、デザインに関する知識は二人ともなく苦労しました。この点は、自分がデザインに関する勉強を少々行い、努力しています。
    - 著作権、利用規約に関する問題が非常にややこしいです。
      - 書籍データを得るためのAPI探し。ある程度のまとまった量のあるレビュー文があるサイトを見つけ、スクレイピングやデータの利用が規約に違反していないかをチェック。書籍の販売リンクを取得するために、各ネットショップのAPI、利用規約をチェック。
      - 利用規約に問題があるため、APIを使用することができず、何ヶ月も開発が止まったことが何回もあります。その度に、問題がなさそうな新たなAPIやサービスを見つけることができているので、現在はなんとか開発が動いています。
    - 推薦アルゴリズムの選定。
      - ライトノベルは年間２０００冊ほど出ており、過去10年分だけをデータベースに登録したとしても、2万冊もの数になります。この数のアイテムについて学習し、即座にレスポンスを返すAPIをスクラッチで開発することはできませんでした。何かいいAPIはないかと探しているところに、近傍探索というアルゴリズムを知り、spotify の annoy というライブラリに出会ったことで、この問題は解決しました。
  - 進捗
      - デザイン案
        - courseraのグーグルUXデザイン、コース1~5を聴講し、作成しました。
        - <img width="662" alt="スクリーンショット 2022-05-26 13 46 34" src="https://user-images.githubusercontent.com/53688020/170417918-babd3cfc-e3c6-470f-9c88-37533bb9e33e.png">
        - <img width="630" alt="スクリーンショット 2022-05-26 13 46 57" src="https://user-images.githubusercontent.com/53688020/170417965-4535a2d7-74e9-421a-bcb8-0f6f6cd4884e.png">
        - <img width="630" alt="スクリーンショット 2022-05-26 13 47 16" src="https://user-images.githubusercontent.com/53688020/170417991-37054d19-1882-431a-b59e-b7b328084ec5.png">
        - <img width="619" alt="スクリーンショット 2022-05-26 13 47 29" src="https://user-images.githubusercontent.com/53688020/170418016-39e36f46-ee10-496a-a59f-e6a85bc273bb.png">
        - ![S__6668290](https://user-images.githubusercontent.com/53688020/167295088-b480fc60-8e8c-4f05-a46b-73a1db6e5988.jpg)
        - [https://www.figma.com/file/zCxLalf7K7Q00WC66BOqTe/recommender?node-id=0%3A1](https://www.figma.com/file/zCxLalf7K7Q00WC66BOqTe/recommender?node-id=0%3A1)
      - トップページ
        - ![localhost_8080_](https://user-images.githubusercontent.com/53688020/167296445-e7f03212-8c94-41a2-b44d-3658f4c7bf84.png)
      - 書籍ページ
        - ![localhost_8080_media_media_id=26](https://user-images.githubusercontent.com/53688020/167296456-d261dd6e-3e8c-49d4-be08-dae99293ef24.png)
      - シリーズページ
        - ![localhost_8080_series_series_id=755](https://user-images.githubusercontent.com/53688020/167296473-4196dc74-af4c-478c-96ba-c3aecb6741b5.png)

- 2022年冬: 「フィボナッチヒープ」というデータ構造の実装
  - ソースコード
    - [https://github.com/nntto/fibonacci_heap](https://github.com/nntto/fibonacci_heap)  
  - 技術
    - rust
 
- 2022年春: ゲーム「7 days to die」のマルチサーバーと管理用サーバーの構築
  - ソースコード
    - [https://github.com/nntto/7dtd_discordbot](https://github.com/nntto/7dtd_discordbot)
  - 概要
    - 7 days to die というゲームにハマり、ec2上にマルチサーバーを構築、discordからサーバーを管理するAPIサーバーを heroku にデプロイしました
  - 技術
    aws ec2, heroku, python, discord.py, aws boto3
    - ec2 上にゲームサーバーを構築
      - ec2 に　SSH　接続し、ゲームのサーバーをダウンロード、MODを導入
    - heroku に管理サーバーを構築
      - discord でコマンドを打つことで、サーバーを管理できる機能を実装
        - サーバーの起動、停止、再起動、サーバーのIPアドレス取得、ec2の使用料金を通知(aws boto3)
      - ゲーム内情報を通知
        - ゲームにプレイヤーがログインした時や、ログアウトした事を通知
        - 節約のため、サーバーの無人状態が10分間続くと、ec2 を自動的に停止
  - 苦労したこと
    - ec2 の権限周りに苦労しました。
      - IAM ユーザーを作成し、権限を割り当てる、という作業には慣れているのですが、boto3 を利用するための権限の名前がわからず若干ハマりかけました
    - 利用料金を抑える
      - 7 days to die に AOO という MOD を導入するのですが、この条件でのサーバーの最低スペックが、24GBRAMという大きなもので、料金を抑えるのに苦労しました。
      - はじめに考えた conoha のレンタルサーバーは、ゲームサーバー用のテンプレートがありサーバー構築が簡単でしたが、一ヶ月の利用料金が3万円と非常に高価だったため断念しました。
      - 今回、サーバーを起動するにあたり、自分たちがゲームをしている間だけの起動で良いので、従量課金性のサーバーを探しました。そこで見つかったのが ec2 でした。さらに、利用料金を抑えるために、スポットインスタンスを利用しました。こうすることで、32GB RAMのサーバーを月額3000円ほどで利用することに成功しました。
