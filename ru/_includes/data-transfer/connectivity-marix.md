Доступные комбинации источников и приемников:



|                                  Источник \ Приемник                                  | [{{ KF }}](../../data-transfer/operations/endpoint/target/kafka.md) | [{{ CH }}](../../data-transfer/operations/endpoint/target/clickhouse.md) | [{{ GP }}](../../data-transfer/operations/endpoint/target/greenplum.md) | [{{ MG }}](../../data-transfer/operations/endpoint/target/mongodb.md) | [{{ MY }}](../../data-transfer/operations/endpoint/target/mysql.md) | [{{ PG }}](../../data-transfer/operations/endpoint/target/postgresql.md) | [{{ ydb-short-name }}](../../data-transfer/operations/endpoint/target/yandex-database.md) | [{{ objstorage-name }}](../../data-transfer/operations/endpoint/target/object-storage.md) |
|:-------------------------------------------------------------------------------------:|:-------------------------------------------------------------------:|:------------------------------------------------------------------------:|:-----------------------------------------------------------------------:|:---------------------------------------------------------------------:|:-------------------------------------------------------------------:|:------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------:|
|          [{{ KF }}](../../data-transfer/operations/endpoint/source/kafka.md)          |                                P^1^                                 |                                   P^1^                                   |                                    -                                    |                                   -                                   |                                  -                                  |                                    -                                     |                                           P^1^                                            |                                           P^1^                                            |
|  [AWS CloudTrail](../../data-transfer/operations/endpoint/source/aws-cloudtrail.md)   |                                  -                                  |                                    К                                     |                                    -                                    |                                   К                                   |                                  К                                  |                                    К                                     |                                             К                                             |                                             -                                             |
|        [BigQuery](../../data-transfer/operations/endpoint/source/bigquery.md)         |                                  -                                  |                                    К                                     |                                    -                                    |                                   К                                   |                                  К                                  |                                    К                                     |                                             К                                             |                                             -                                             |
|       [{{ CH }}](../../data-transfer/operations/endpoint/source/clickhouse.md)        |                                  -                                  |                                    К                                     |                                    -                                    |                                   -                                   |                                  -                                  |                                    -                                     |                                             -                                             |                                             -                                             |
|                                       EventHub                                        |                                P^1^                                 |                                   P^1^                                   |                                    -                                    |                                 P^1^                                  |                                P^1^                                 |                                   P^1^                                   |                                           P^1^                                            |                                             -                                             |
|        [{{ GP }}](../../data-transfer/operations/endpoint/source/greenplum.md)        |                                  -                                  |                                   К^1^                                   |       [К^1^](../../data-transfer/tutorials/managed-greenplum.md)        |                                   -                                   |                                  -                                  |                                   К^1^                                   |                                             -                                             |                                             -                                             |
|         [{{ MG }}](../../data-transfer/operations/endpoint/source/mongodb.md)         |                                  -                                  |                                    -                                     |                                    -                                    |        [КР](../../data-transfer/tutorials/managed-mongodb.md)         |                                  -                                  |                                    -                                     |                                             -                                             |                                           К^1^                                            |
|          [{{ MY }}](../../data-transfer/operations/endpoint/source/mysql.md)          |                                  -                                  |                                    КР                                    |                                    -                                    |                                   -                                   |        [К](../../data-transfer/tutorials/managed-mysql.md)Р         |                                    -                                     |                                            КР                                             |                                           К^1^                                            |
|          [Oracle](../../data-transfer/operations/endpoint/source/oracle.md)           |                                  -                                  |                                  КР^1^                                   |                                    -                                    |                                   -                                   |                                  -                                  |                                  КР^1^                                   |                                             -                                             |                                             -                                             |
|       [{{ PG }}](../../data-transfer/operations/endpoint/source/postgresql.md)        |         [P^1^](../../data-transfer/tutorials/kafka-cdc.md)          |      [КР^1^ ](../../data-transfer/tutorials/rdbms-to-clickhouse.md)      |       [К^1^](../../data-transfer/tutorials/managed-greenplum.md)        |                                   -                                   |                                  -                                  |        [К](../../data-transfer/tutorials/managed-postgresql.md)Р         |                                            КР                                             |                                           К^1^                                            |
|              [S3](../../data-transfer/operations/endpoint/source/s3.md)               |                                  -                                  |                                    К                                     |                                    -                                    |                                   К                                   |                                  К                                  |                                    К                                     |                                             К                                             |                                             -                                             |
 |                                 {{ ydb-short-name }}                                  |                                  -                                  |                                   К^1^                                   |                                    -                                    |                                   -                                   |                                  -                                  |                                    -                                     |                                             -                                             |                                             -                                             |
 | [{{ yds-full-name }}](../../data-transfer/operations/endpoint/source/data-streams.md) |                                  -                                  |                                   Р^1^                                   |                                    -                                    |                                 Р^1^                                  |                                  -                                  |                                   Р^1^                                   |                                           P^1^                                            |                                           P^1^                                            |





К — Копирование
Р — Репликация
КР — Копирование и репликация
^1^ Функциональность находится на стадии [Preview](../../overview/concepts/launch-stages.md).
^2^ Функциональность находится на стадии [Preview](../../overview/concepts/launch-stages.md) и предоставляется по запросу. Обратитесь в [техническую поддержку]({{ link-console-support }}) или к вашему аккаунт-менеджеру.
