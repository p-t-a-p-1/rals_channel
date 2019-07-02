# 元となるイメージ　docker pull で取ってきた
FROM alpine:3.10

# apk add で必要なパッケージをインストール
# laravelの要件を満たすものを入れる
# @see https://readouble.com/laravel/5.8/ja/installation.html
RUN apk add php7-openssl \
php7-tokenizer \
php7-pdo_mysql \
php7-mbstring \
php7-tokenizer \
php7-xml \
php7-json \
php7-phar \
php7-fileinfo \
php7-dom \
php7-xmlwriter \
php7-session

# composerを入れる phpのパッケージ管理ツール
# @see https://getcomposer.org/download/
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
php -r "if (hash_file('sha384', 'composer-setup.php') === '48e3236262b34d30969dca3c37281b3b4bbe3221bda826ac6a9a62d6444cdb0dcd0615698a5cbe587c3f0fe57a54d8f5') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
php composer-setup.php && \
php -r "unlink('composer-setup.php');"

# ルートにあるcomposer.pharを環境変数内にcomposerとして移動 = composerで実行できるようにする
RUN mv /composer.phar /usr/local/bin/composer

# 作業用のディレクトリ
WORKDIR /home

# コンテナ実行時に行うコマンド
CMD ["php", "artisan", "serve", "--host", "172.17.0.3"]