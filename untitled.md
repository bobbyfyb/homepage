# MS MARCO Conversational Search Session dataset 説明文書

## MS MARCOについて

MS MARCO \(Microsoft Machine Reading Comprehension\)とは、マイクロソフトがNIPS 2016で発表した、機械読解、質問応答、文書ランキングや会話検索などの情報検索において深層学習を応用する研究分野に注目するデータセットの家族というものである。これらのデータセットはマイクロソフトのサーチエンジンBingのログから抽出したデータで組み立てたものである。

* MS MARCOの公式サイト：https://microsoft.github.io/msmarco/
* MS MARCO: A Human Generated MAchine Reading COmprehension Dataset Paper URL : [https://arxiv.org/abs/1611.09268](https://arxiv.org/abs/1611.09268)

## MS MARCO Conversational Search Session datasetについて

Bingの検索ログから人工的に会話セッションを作って、真実の検索会話のように使えるのを目指す公開のデータセットである。各セッションは一つ以上のクエリーで構成され、マルチターンの会話を表している。全てのクエリーがquery embeddingでembedding vectorに変換して、ニューラルネットワークなどの技術で用いられる。

以下は一つセッションの例である：

marco-gen-dev-572

1. stock price tesla
2. fb stock price home depot stock price t
3. amazon stock price
4. nxp semiconductors stock price

## データセットのタスク

セッションのクエリー歴史 q1, q2, …, q\(n-1\)の上で、次のクエリーq\(n\)を予測する

## データセットのイニシャル

[https://github.com/microsoft/MSMARCO-Conversational-Search](https://github.com/microsoft/MSMARCO-Conversational-Search)に参考しよう

## 参考サイト

MS MARCO website: [https://microsoft.github.io/msmarco/](https://microsoft.github.io/msmarco/)

Github repo: [https://github.com/microsoft/MSMARCO-Conversational-Search](https://github.com/microsoft/MSMARCO-Conversational-Search)

