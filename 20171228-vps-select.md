
# Compute + ObjectStorage で、独自ドメイン静的サイト構築

## 用途

- 対象サイトは、自分用メモ(blog)と写真サイト(blog+固定ページ)
- jekill or hugo or hexo で Markdown から html ファイル生成、独自ドメインで公開する。
  - アンケートやカートシステムは、他サービス(サイト)との連携にて実現する。本システムの対象外。

## 要件、要検討事項

- Markdown はどこででも書けるようにしたい。
  - 書いた Markdown を、どこに集約するか?
  - 可能であれば、この段階のファイルを公開したくない。
    - 検索エンジンに拾ってほしくないため。
  - 書いた Markdown を、端末間でどうやって共有するか。
- 生成処理から ObjectStorage への掲載までを、自動にしたい。
  - Compute で生成処理を実施
  - Google cloud shell でもいい
  - 自宅の RaspberryPi でもいい
  - Github から CI もアリでは?
- 生成したコンテンツを ObjectStorage で公開。
  - 外部から、独自ドメインで、参照可能な領域であること。
  - 外部or内部から、コンテンツの差し替えが可能であること。
  - 可能であれば、アクセスログを保存してくれること。
  - 自分用メモは、更新アピールのため gitlab.io に掲載。
  - 写真サイトは、s3的な場所の方がいいかも。

- 独自ドメインが必要。ドメイン管理費用は本項対象外。

- デプロイは CircleCI にやらせればよい?
  - Github から CI で Github へ掲載。

- https が必要なら、少なくとも Github と S3 が落ちる。

## 選択肢

- Amazon - EC2 + S3
- GCP - Cloud Shell + Cloud Storage
- Netlify
- Firebase Hosting
