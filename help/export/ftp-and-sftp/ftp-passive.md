---
description: アクティブモードとパッシブモードの FTP では、ポート接続の確立方法が異なります。選択したモードに適したファイアウォール設定が必要になります。
keywords: ftp;sftp
title: FTP Passive モードを使用
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 85%

---

# FTP Passive モードを使用

アクティブモードとパッシブモードの FTP では、ポート接続の確立方法が異なります。選択したモードに適したファイアウォール設定が必要になります。

アドビでは、より安全にデータ転送を行えるパッシブ FTP を使用しています。パッシブモードでは、ファイル転送プロトコル（FTP）サーバープログラムではなく、FTP クライアントによってデータのフローがセットアップされ、開始されます。AdobeFTP に接続できない場合は、必ずパッシブモードを使用してください。
