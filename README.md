# 実行コマンド例
### ライブラリインストール
docker compose exec -it laravel composer require openai-php/laravel
### ライブラリ反映
docker compose exec -it laravel php artisan vendor:publish --provider="OpenAI\Laravel\ServiceProvider"
### マイグレーション
docker compose exec -it laravel php artisan migrate
### npm
docker compose exec -it laravel npm run dev