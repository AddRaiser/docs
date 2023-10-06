# Как создать бэкап виртуальной машины с возможностью отката


## Описание сценария {#case-description}

Необходимо создать бэкап виртуальной машины, предусматривающий возможность отката.

## Решение {#case-resolution}

Можно самостоятнельно настроить [создание снимков дисков по расписанию](../../../compute/operations/snapshot-control/create-schedule), но откатить изменения виртуальной машины с помощью снимка диска не получится. Для этого необходимо создать новую  ВМ из снимка. Как это сделать, мы пишем [здесь](../../../compute/operations/vm-create/create-from-snapshots).

Также рекомендуем сервис {{ backup-full-name }} – в нём есть возможность делать резервные копии ВМ по расписанию. Сейчас поддерживается создание резервных копий виртуальных машин на базе Ubuntu и CentOS. Более подробно вы можете прочитать в нашей [документации](../../../backup/concepts/).