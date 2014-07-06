# mext_gdal on vagrant

これは基盤地図情報対応GDAL/OGR(mext_gdal)をvagrant上でビルドと実行を行うものです。

## なぜ必要か

基盤地図情報対応GDAL/OGRはバイナリリリースがないMac OS X上では開発環境を整えてビルドするのが面倒(といういろんな人が昔やったとかそういう話が多すぎてなんだか地獄絵図っぽいとか)で、非開発者向けが基盤地図情報とかを気軽に変換できるものを作ったほうが人類にとって良いかなと思ったので、酒飲みながら作りました。

## 使い方

### 初回の作業

1. [Downloads – Oracle VM VirtualBox](https://www.virtualbox.org/wiki/Downloads) からVirtualBoxのダウンロードとインストールを行う
2. [Download Vagrant - Vagrant](http://www.vagrantup.com/downloads.html) からVagrantのインストーラをダウンロードしてインストールをする
3. このプロジェクトをcloneもしくはダウンロードする
4. [FOSS4G を活用した衛星データ利用のためのオープン・リソースの構築 |OSGeo.JP](http://www.osgeo.jp/foss4g-mext/) から基盤地図対応GDAL/OGRの1.10.0のソースコード(mext_gdal.1.10.0.tar.gz)をダウンロードして、このプロジェクトのディレクトリ直下に置く
5. filesディレクトリ内にShapeファイルに変換したい基盤地図情報のデータ(JPGIS形式, 拡張子はxml)を置く
6. ターミナルから vagrant up を実行する。最初は環境構築も行うため、アニメを鑑賞するなり時間を潰しておく
7. 処理が終わればoutputディレクトリに変換後のファイルが転がっている(はず)

### 二回目以降

1. filesディレクトリ内にShapeファイルに変換したい基盤地図情報のデータ(JPGIS形式, 拡張子はxml)を置く
2. outputディレクトリを予め空にしておく(しなくてもいいけど、そうしないとファイルがごちゃごちゃするのでおすすめできない)
3. ターミナルから vagrant provision を実行する
4. 処理が終わればoutputディレクトリに変換後のファイルが転がっている(はず)

## ファイル構成

こういう感じ

    .
    ├── README_ja.md (この文書)
    ├── Vagrantfile (vagrantで使うファイル)
    ├── files (基盤地図情報のデータを置くディレクトリ)
    ├── mext_gdal.1.10.0.tar.gz (基盤地図対応GDAL/OGRのソースコード)
    └── output (出力先)

## 助けてくれ

このREADME_ja.mdの文書が雑すぎるのでまともな説明にしてPull Request送ってほしい(もしくは諦めましょう)。

## 参考にしたプロジェクト

- [miurahr/libreoffice-build-ubuntu-vagrant](https://github.com/miurahr/libreoffice-build-ubuntu-vagrant)

## 開発に必要なもの

- vagrantの知識
- 他の人のVagrantfileをさらっとパクる根性
- 酒
- インターネット
