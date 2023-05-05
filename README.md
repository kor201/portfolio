# 実行コマンド例
### ライブラリインストール
docker compose exec -it laravel composer require openai-php/laravel
### ライブラリ反映
docker compose exec -it laravel php artisan vendor:publish --provider="OpenAI\Laravel\ServiceProvider"
### マイグレーション
docker compose exec -it laravel php artisan migrate
### npm
docker compose exec -it laravel npm run dev
### https化key作成
（ローカルで）openssl genrsa -aes128 2048 > server.key
### https化csr作成
(コンテナ内で)openssl req -new -key server.key > server.csr
### https化crt作成
(コンテナ内で)openssl x509 -in server.csr -days 365 -req -signkey server.key > server.crt
### https化パスフレーズ作成
echo "設定したパスフレーズ" > server.password
### webサーバlog取得
docker-compose logs nginx