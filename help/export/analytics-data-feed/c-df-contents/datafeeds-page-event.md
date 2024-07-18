---
description: page_event の値に基づいてヒットタイプを判別する参照テーブル。
keywords: データフィード;ページ;イベント;page_event;post_page_event
title: ページイベント参照
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 100%

---

# ページイベント参照

page_event の値に基づいてヒットタイプを判別する参照テーブル。

| ヒットタイプ | `page_event` の値 | `post_page_event` の値 |
| --- | --- | --- |
| ページビュー数 | 0：モバイル SDK のすべてのページビューコールと `trackState` コール | `page_event` と同じ値 |
| リンクトラッキング | 10：モバイル SDK のカスタムリンクと `trackAction` コール<br>11：ダウンロードリンク<br>12：離脱リンク | 100：モバイル SDK のカスタムリンクと `trackAction` コール<br>101：ダウンロードリンク<br>102：離脱リンク |
| マイルストーンビデオ | 31：メディア開始<br>32：メディアの更新（他の変数処理なし）<br>33：メディアの更新（他の変数を使用） | 76：メディア開始<br>77：メディアの更新（他の変数処理なし）<br>78：メディアの更新（他の変数を使用） |
| ハートビートビデオ | 50：メディアストリーム開始（Primetime 以外）<br>51：メディアストリーム終了（Primetime 以外）<br>52：メディアストリームスクラビング（Primetime 以外）<br>53：メディアストリームキープアライブ（Primetime 以外）<br>54：メディアストリーム広告開始（Primetime 以外）<br>55：メディアストリーム広告終了（Primetime 以外）<br>56：メディアストリーム広告スクラビング（Primetime以外）<br>60：Primetime メディアストリーム開始<br>61：Primetime メディアストリーム終了<br>62：Primetime メディアストリームスクラビング<br>63：Primetime メディアストリームキープアライブ<br>64：Primetime メディアストリーム広告開始<br>65：Primetime メディアストリーム広告終了<br>66：Primetime メディアストリーム広告スクラビング | `page_event` と同じ値 |
| 調査 | 40：調査から生成された任意の呼び出し | 80：調査から生成された任意の呼び出し |
| Analytics for Target | 70：ヒットに Target アクティビティデータを含む | `page_event` と同じ値 |
