# LD-NRTP
LSX-Dodgers NRTDRV Player

# 概要
LD-NRTP は、X1用のOS、LSX-Dodgersにて、OPM+PSGドライバ「NRTDRV」を利用してNRD形式の楽曲再生を行うためのツールです。

NRTDRVを内部に組み込んでおり、簡易演奏モニタにて再生状態を表示しつつ再生します。

対象のLSX-Dodgers: 1.52(以降)

# 使い方
```
  NRTP [filepath(.NRD)]
    filepath: NRDファイルのパスを指定します。拡張子がNRDの場合、省略可能です。
```

再生したいNRDファイルのパスを第一引数に渡す事で、そのデータを再生します。
ESCキーを押す事で再生を終了します。

その他の挙動はNRTDRVの簡易演奏モニタ準拠となりますが、テストトーン再生には非対応です。

# ビルド方法

**現在LD-NRTPが対応しているNRTDRVは 2020/01/11版 NRTDRV_200111.ZIP になります。**

[NRTDRVのページ](http://nrtdrv.sakura.ne.jp) からNRTDRV一式をダウンロードし、
アーカイブ内のソースファイルから、下記のものを、LD-NRTPのフォルダにコピーしてください。

* NRTDRV.ASM
* IPLPATCH.ASM
* OPTION.ASM

コピー後、管理者権限を与えたコマンドプロンプトにて「patch_ailz80.bat」を実行し、パッチをあてます
(Z80アセンブラ [AILZ80ASM](https://github.com/AILight/AILZ80ASM) 用にソースを変換しつつ、LD-NRTPにあわせた内容に書き換えています)。

続いて「build_ailz80.bat」を実行する事で、LD-NRTPの実行ファイル「NRTP.COM」が作成されます。

# 謝辞
LD-NRTP は、NRTDRVを単純にアプリ化しただけのプログラムであるため、このツールによる良い部分は全て [NRTDRV developers](http://nrtdrv.sakura.ne.jp/index.cgi?page=FrontPage#p3) 様の手によるものです。

# History
* Version 202211-001 (2022/11/17)
  * LSX-Dodgers 1.52対応
* Version 202208-001 (2022/8/23)
  * 初版
