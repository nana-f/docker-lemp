# docker-lemp
- LEMP環境構築
#
# docker-lemp
## リモートリポジトリ先を変更する場合
git remote set-url origin {RemoteRepository}

git remote -v
#
## デフォルトブランチの設定
git config --global init.defaultBranch {BranchName}
#
## コミットプッシュ
git status

git add .

git status

git commit -m "feat create docker db container"

git log

git push
##### ※ 指定のブランチへプッシュ
git push -u origin {BranchName}
#
## LEMP環境構築手順
##### (SHA-1:ac70891e03f460652498451ebc2dc6857f58c502)
#### ※ powershellにて作業
docker compose build

docker compose up -d

docker compose exec php bash

composer create-project "laravel/laravel=9.*" .

chmod -R 777 storage bootstrap/cache

http://127.0.0.7:8080/

#### ※1 修正

docker compose exec php bash

php artisan migrate

docker compose exec db bash

mysql -u{USER_NAME} -p{USER_PASSWORD}

use db;

show tables;

http://127.0.0.7:3000/

#### - 構築完了 -

#### ※1 src \ .envの該当項目を以下に修正
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=db
    DB_USERNAME=db_user
    DB_PASSWORD=db_pwd
