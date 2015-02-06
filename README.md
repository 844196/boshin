# BOSHIN
[![author](http://img.shields.io/badge/author-844196-blue.svg?style=flat)](https://github.com/844196)
[![version](http://img.shields.io/github/tag/844196/boshin.svg?style=flat&label=version)](https://github.com/844196/boshin/releases)
[![license](http://img.shields.io/badge/license-MIT-red.svg?style=flat)](LICENSE)
[![issue](http://img.shields.io/github/issues/844196/boshin.svg?style=flat)](https://github.com/844196/boshin/issues)

![](http://33.media.tumblr.com/96e3db1b52b435be7d06bcf767639510/tumblr_njck065NS31s7qf9xo1_1280.gif)

スクショを撮影してタイトルバーとかをトリミングしてくれるやつ

## SYNOPSIS
```
boshin [-vh] [-i input_file] [output_path]
```

## DESCRIPTION

- このスクリプトは撮影したスクリーンショットをImageMagickでステータスバーを取り除いた上でカレントディレクトリに出力します。
- `output_path`が指定されていない場合、ファイルネームは撮影日時になります。
- このスクリプトは正常終了時、自身の後ろにパイプが接続されている場合は、加工し出力したスクリーンショットのファイルパスを標準出力します。
    - パイプがない場合は標準出力しません。

## USAGE

1. ターミナル等から`boshin`を呼び出します

    ```shellsession
    $ boshin
    ```

2. ウィンドウ選択モードになるので、撮影したウィンドウをクリックします
3. カレントディレクトリ（`output_path`を指定した際は指定のパス）にスクリーンショットが保存されます

## OPTIONS

- `-v`, `--version`
    - バージョンを標準エラー出力に表示し、正常終了します。
- `-h`, `--help`
    - ヘルプを標準エラー出力に表示し、正常終了します。
- `-i PATH`, `--input PATH`
    - 撮影したスクリーンショットではなく、既存の画像ファイルに対し加工を施したい際に使用します。

## EXIT STATUS

|   |説明                                                        |
|:-:|:-----------------------------------------------------------|
| 0 |正常終了                                                    |
| 2 |ImageMagickへのパスが通っていないか、存在しません           |
|255|存在しないオプション、またはオプションの引数に不備があります|

## NOTES

- このスクリプトはMacでしか動作しません
- 動作にはImageMagickが必要です

## EXAMPLE

- 出力先を指定して実行
    ```shellsession
    $ boshin ./ss.png
    ```

- 既存のスクリーンショットに対して実行
    ```shellsession
    $ boshin --input ~/Pictures/screenshots/old.png ./new.png
    ```

- 撮影した結果をすぐに確認する
    ```shellsession
    $ boshin | xargs open
    ```


## AUTHORS
Masaya Tk (<https://github.com/844196>)
