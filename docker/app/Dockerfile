# ベースイメージ
FROM php:8.0-fpm

# コンテナ内サーバ環境変数を設定
ENV TZ Asia/Tokyo

RUN apt-get update && \
	apt-get install -y git unzip libzip-dev libicu-dev libonig-dev && \
	docker-php-ext-install intl pdo_mysql zip bcmath

# ini ファイルのコピー
COPY ./docker/app/php.ini /usr/local/etc/php/php.ini

# composer をインストール
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

WORKDIR /app
