# smile_work03 WordPress
創造社デザイン専門学校スマイル工房　WordPress

## WordPressのインストールと安全対策
### MySQLの準備
MySQLにWordPress専用のDBを作成する。
- phpMyAdminを使用する方法
- MySQLモニタを使用する方法
- MySQL Userの設定

### WordPressをダウンロード
https://ja.wordpress.org/download/

### 初回設定
- wpconfig.phpに直接データベース情報を設定する方法
- ブラウザ経由でデータベース情報を設定する方法

### WordPress周知の問題点

### インストールしたらまず設定すること
- ログインURLの変更(SiteGuard WP)
- ユーザー情報更新
- サイトのURL/?author=1

### ログインURLの変更
SiteGuard WPプラグインを導入、有効かして初期設定をする。

### ユーザー情報の更新
WordPressのユーザープロフィールの更新

### authorを隠す
funcstions.phpに以下を書き足す。
```
function disable_author_archive_query() {
  if( preg_match('/author=([0-9]*)/i', $_SERVER['QUERY_STRING']) ){
    wp_redirect( home_url() );
    exit;
  }
}
add_action('init', 'disable_author_archive_query');
```
### SEOプラグインは必要？不要？


