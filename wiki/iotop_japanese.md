# [Linux] C Shell (csh) iotopの使い方: 入出力の監視

## Overview
iotopは、システムの入出力（I/O）をリアルタイムで監視するためのツールです。このコマンドを使用することで、どのプロセスがディスクI/Oを多く使用しているかを確認することができます。

## Usage
基本的な構文は以下の通りです。

```csh
iotop [options] [arguments]
```

## Common Options
- `-o` : I/Oを行っているプロセスのみを表示します。
- `-b` : バッチモードで実行し、出力を標準出力に送ります。
- `-n NUM` : NUM回の更新後に終了します。
- `-d SEC` : SEC秒ごとに更新します。

## Common Examples
以下に、いくつかの実用的な例を示します。

1. I/Oを行っているプロセスを表示する：
   ```csh
   iotop -o
   ```

2. バッチモードでI/O情報を表示する：
   ```csh
   iotop -b -n 5
   ```

3. 2秒ごとに更新し、I/Oを行っているプロセスを表示する：
   ```csh
   iotop -o -d 2
   ```

## Tips
- iotopを実行するには、通常、root権限が必要です。`sudo`を使用して実行することをお勧めします。
- 長時間の監視が必要な場合は、バッチモードを利用してログファイルに出力することが便利です。
- 特定のプロセスのI/Oを監視したい場合は、`grep`と組み合わせて使用することができます。