FROM php:7.2-fpm

# curlコマンドを使ってComposerをインストール
# apt-getコマンドでgit, zip, unzip, vimをインストール
# docker-php-ext-installコマンド（コンテナイメージに事前に圧縮されて入っている拡張機能を解凍・インストールするコマンド）を使ってPDOをインストールするスクリプトを記述
RUN cd /usr/bin && curl -s http://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer
RUN apt-get update \
&& apt-get install -y \
git \
zip \
unzip \
vim
RUN apt-get update \
    && apt-get install -y libpq-dev \
    && docker-php-ext-install pdo_mysql pdo_pgsql

# RUNなどの命令を実行するときの作業ディレクトリを指定しています。
WORKDIR /var/www/html