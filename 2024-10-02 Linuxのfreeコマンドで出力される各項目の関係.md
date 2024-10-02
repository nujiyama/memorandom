# Linuxのfreeコマンドで出力される各項目の関係

以下のtotal、used、free等の関係。

```
$ free -h
              total        used        free      shared  buff/cache   available
Mem:          5.6Gi       2.8Gi       532Mi       283Mi       2.3Gi       2.3Gi
Swap:            0B          0B          0B
$
```

Perplexityに聞いたところの抜粋としては以下のような感じ。

## `free`コマンドの出力項目

- **total**: システムで利用可能な物理メモリ全体の量を示します。これはインストールされているRAMの総量です。
- **used**: 現在使用中のメモリ量を示します。この値は、実際にプロセスによって使用されているメモリを表しています。
- **free**: 未使用で即座に利用可能なメモリ量です。これはシステムがすぐに使用できるメモリを示しますが、Linuxでは通常この値は小さくなります。
- **shared**: 一部のプロセス間で共有されているメモリ量を示します。この値は通常無視しても問題ありません。
- **buff/cache**: バッファとキャッシュに使用されているメモリ量です。Linuxはパフォーマンス向上のために空きメモリをバッファやキャッシュとして利用しますが、このメモリは必要に応じて他のプロセスに再割り当てされます。
- **available**: 新しいプロセスが開始されたり既存のプロセスが拡張されたりする際に利用可能な推定メモリ量です。この値は`free`よりも重要で、システムが実際にどれだけの新しい負荷を処理できるかを示します[1][2][3]。

## 各項目の関係

`free`コマンドの出力に基づく各項目の関係を式で表すと、以下のようになります。

- **Mem:**
  - $$\text{total} = \text{used} + \text{free} + \text{buff/cache}$$
  - $$\text{available} = \text{free} + \text{buff/cache} - \text{shared}$$

- **Swap:**
  - $$\text{total swap} = \text{used swap} + \text{free swap}$$

## つまりこうか？

ここではMemのみ考える。うまい描き方が思いつかないのだが…

```
+---------------------------+
| total                     |
+------+------+-------------+
| used | free | buff/cache  |  totalの内訳はused、free、buff/cache
|      +------+----+--------+
|      | available | shared |  freeとbuff/cacheの一部がavailable、残りがshared
+------+-----------+--------+ 
```

