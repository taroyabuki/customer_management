customer_management
===================

マッキーソフト株式会社『PHPシステム開発の教科書』（技術評論社, 2012）の顧客管理アプリケーション。

##インストール

1. http://www.apachefriends.org/jp/xampp-windows.html からXAMPP Windows版のインストーラをダウンロードし、実行する。インストールの様子を撮影した動画がhttp://youtu.be/WPb3xVddtxg にあるが、Microsoft Visual C++ 2008 SP1 Redistributabe Package (x86)はインストールしなくても大丈夫かもしれない。
1. ApacheとMySQLを起動する。
1. https://github.com/taroyabuki/customer_management/archive/master.zip をダウンロードし、`C:/xampp/htdocs`に展開する。（`C:/xampp/htdocs/cake/app/...`というディレクトリ構造になればよい。）
1. [http://localhost/phpmyadmin/](http://localhost/phpmyadmin/) にアクセスし、「インポート」をクリック、`C:/xampp/htdocs/cake/custom/customer_management_preparation.sql`をインポートする。（ファイルを指定する以外はデフォルトのままでよい。）
1. [http://localhost/cake/users/add](http://localhost/cake/users/add) にアクセスし、管理ユーザを作成する(UsernameとPasswordだけ入力すればよい)。
1. [http://localhost/cake/](http://localhost/cake/) にアクセスし、上で作成したユーザ情報を入力すると、アプリを利用することができる。

###オプショナル（必須ではない）

####Unicode追加面への対応

「![𠮷](http://www.unicode.org/cgi-bin/refglyph?24-20BB7)」のような文字を使いたい場合は、途中で以下の作業を行う。

1. `customer_management_preparation.sql`の`utf8`を`utf8mb4`に置換する。
1. `database.php`の`'encoding' => 'utf8',`を`'encoding' => 'utf8mb4',`に置換する。
