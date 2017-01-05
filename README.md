kibana-elasticsearch-playbook
============================================================

# 概要

Elasticsearch/Logstash/KibanaをインストールするためのAnsible playbook
inventry groupとしてaio_standaloneを指定した場合を除いてすべてのノードがクラスタの一部となる。
aio_standaloneに指定したノードは、それぞれのノードが1つの独立したクラスタとなる

## Inventry group設定

- elk

  Elasticseach/Logstash/Kibanaをすべて動作させるノードを指定する(すべてのクラスタが1クラスタの一部となる)

- elasticsearch

  Elasticseachを動作させるノードを指定する(すべてのクラスタが1クラスタの一部となる)

- kibana

  Kibanaを動作させるノードを指定する(すべてのクラスタが1クラスタの一部となる)

- logstash

  Logstashを動作させるノードを指定する(すべてのクラスタが1クラスタの一部となる)

- elasticseach_nodes

  内部処理用のInventry group(ノードは指定しない)

- aio_standalone

  独立したAll-in-Oneのクラスタを構築する

# 動作確認済み環境

- RHEL7
- CentOS7

# 設定

- es_cluster_name           # Elasticsearchのクラスタ名を指定する(aio_standaloneの場合はクラスタ名にホスト名が加えられる)
- xpack_security_enabled    # xpackのsecurity機能の有効無効を設定する(サブスクリプションがない場合1ヶ月しか使用できない)
- xpack_monitoring_enabled  # xpackのmonitor機能の有効無効を設定する(サブスクリプションがない場合1ヶ月しか使用できない)
- xpack_graph_enabled       # xpackのgraph機能の有効無効を設定する(サブスクリプションがない場合1ヶ月しか使用できない)
- xpack_watcher_enabled     # xpackのwatcher機能の有効無効を設定する(サブスクリプションがない場合1ヶ月しか使用できない)
- xpack_reporting_enabled   # xpackのreporting機能の有効無効を設定する(サブスクリプションがない場合1ヶ月しか使用できない)

# 依存関係

- common

# TODO

  - KibanaとElasticsearchノードの分離を可能とする
  - 細かくノードの役割を指定できるようにする
