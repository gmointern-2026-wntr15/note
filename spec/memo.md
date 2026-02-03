天秤AIのような複数のLLMの出力を比較するプロダクトを以下の流れでチーム開発していきます。 
チームで挨拶 進捗表確認、役割分担、リーダの相談 GitHub Repogitory、プライベート化、メンター共有 「アプリケーションアーキテクチャ」の相談、決定 「DB設計」、「インフラ設計」着手 （→ 素案作成） 夕会 「アプリケーションアーキテクチャ」の進捗状況説明 （もし「DB設計」、「インフラ設計」など進捗あれば説明）

要件 ・2つのLLM同時実行 ・履歴 ・トークン量集計 （チャット単位で金額感を　画面に表示） ※基本的にやらないこと ・ログイン ・3つ以上のLLM ・「基本」、「高度」の分類 ・壁打ち、やり直す、リセット

これをつくりますが、

* Framework
    * Frontend: React (シンプルな構成)
        * React Router (ルーティング最適化)
        * Vite (Build高速化)
            * SSRを行うか
    * Backend: Fastify (高速処理)


* Infrastructure (AWS)
    * Server: 
        * フロント：Amplify Hosting
        * バック：ECS on Fargate
            * 運用上はAmplifyを通したデプロイ
    * DB
        * RDB: Aurora (MySQL8.0)
        * NoSQL: DynamoDB (チャット履歴)
    * （Cache: ElastiCache for Redis (チャット履歴)）
