## 1.プロセスについて学ぼう

#### プロセスってなに？
- 実行中のプログラムのこと
  - コマンドを実行すると、実行ファイルをメモリに格納して、メモリ上でCPUがプログラムを実行する。一つ実行すると新しいプロセスが一つ作られる

----

## 2.プロセスを表示しよう【psコマンド】

#### psコマンド
- 実行中のプロセスを表示するコマンド
  - 何の略？：process status
  - 書式：ps [オプション

#### オプション
- aux：全ユーザーのプロセスを、詳細情報を合わせて表示
  - x：psコマンドを実行したユーザーの全てのプロセス
  - a：全てのユーザーのプロセス
  - u：詳細情報を合わせて表示する

----

## 3.ジョブについて学ぼう

#### ジョブってなに？
- まとめて実行されるプロセスの集まりがジョブ。シェルごとに管理される
- ジョブとプロセスの違い
  - プロセスはOS全体で統一して管理される。システムが自動で実行しているプログタムや他のユーザーが実行しているコマンドを一括して管理
  - ジョブは、そのジョブを実行するシェルで管理される

----

## 4.ジョブの状態を変更しよう【fg.bgコマンド】

#### バックグラウンドとフォアグラウンド
- シェルの画面がいでコマンドを実行することをバックグラウンド、シェルの画面内で実行することをフォアグラウンドと呼ぶ

#### jobsコマンド
- 現在のジョブの一覧を表示するコマンド
  - 何の略？：jobs
  - 書式：jobs

#### fgコマンド
- ジョブをフォアグラウンドにするコマンド
  - 何の略？：foreground
  - 書式：fg %<ジョブID>
  - 具体例：fg %1

#### bgコマンド
- ジョブをバックグラウンドにするコマンド
  - 何の略？：background
  - 書式：bg %<ジョブID>
  - 具体例：bg %1

----

## 5.プロセス・ジョブを終了しよう【killコマンド】

#### killコマンド
- ジョブやプロセスを終了させるコマンド
  - 何の略？：kill process
  - 書式：kill [オプション] %<ジョブID>、kill [オプション] <プロセスID>
- 補足
  - 正確には、killコマンドはシグナルを送信するコマンド
  ```
  kill -<シグナル> <プロセスID>
  ```
  - デフォルトでは、TERMという終了を指示するシグナルを送信している
  - 時々使うのはSIGKILLという強制終了のコマンド
  ```
  kill -SIGKILL 4965
  ```