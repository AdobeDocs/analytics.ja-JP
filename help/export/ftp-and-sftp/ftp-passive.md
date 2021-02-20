---
description: アクティブモードとパッシブモードの FTP では、ポート接続の確立方法が異なります。選択したモードに適したファイアウォール設定が必要になります。
keywords: ftp;sftp
title: FTP Passive モードを使用
uuid: e56e937e-ec42-45ec-ae8e-8a8ea1b76f3f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 98%

---


# FTP Passive モードを使用

アクティブモードとパッシブモードの FTP では、ポート接続の確立方法が異なります。選択したモードに適したファイアウォール設定が必要になります。

アドビでは、より安全にデータ転送を行えるパッシブ FTP を使用しています。パッシブモードでは、ファイル転送プロトコル（FTP）サーバープログラムではなく、FTP クライアントによってデータのフローがセットアップされ、開始されます。アドビの FTP への接続で問題がある場合は、パッシブモードを使用していることを確認してください。
