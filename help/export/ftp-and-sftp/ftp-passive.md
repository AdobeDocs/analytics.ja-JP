---
description: アクティブモードとパッシブモードの FTP では、ポート接続の確立方法が異なります。選択したモードに適したファイアウォール設定が必要になります。
keywords: ftp;sftp
title: FTP Passive モードを使用
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '101'
ht-degree: 100%

---

# FTP Passive モードを使用

アクティブモードとパッシブモードの FTP では、ポート接続の確立方法が異なります。選択したモードに適したファイアウォール設定が必要になります。

アドビでは、より安全にデータ転送を行えるパッシブ FTP を使用しています。パッシブモードでは、ファイル転送プロトコル（FTP）サーバープログラムではなく、FTP クライアントによってデータのフローがセットアップされ、開始されます。アドビの FTP への接続で問題がある場合は、パッシブモードを使用していることを確認してください。
