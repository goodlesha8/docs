---
title: Пошаговые инструкции для {{ backup-full-name }}
description: На странице представлен список пошаговых инструкций для {{ backup-name }}.
---

# Пошаговые инструкции для {{ backup-name }}

## Управление виртуальными машинами в {{ backup-name }} {#connect-vm}

* [Создать виртуальную машину на Linux с подключением к {{ backup-name }}](create-vm.md)
* [Создать виртуальную машину Windows Server с подключением к {{ backup-name }}](create-vm-windows.md)
* [Подключить виртуальную машину на Linux к {{ backup-name }}](connect-vm-linux.md)
* [Подключить виртуальную машину на Linux с OS Login к {{ backup-name }}](connect-vm-oslogin-linux.md)
* [Подключить виртуальную машину на Windows Server к {{ backup-name }}](connect-vm-windows.md)
* [Обновить подключение виртуальной машины к {{ backup-name }}](refresh-connection.md)
* [Обновить агент резервного копирования {{ backup-name }} на виртуальной машине](update-backup-agent.md)
* [Обновить подключение виртуальной машины на Linux с OS Login к {{ backup-name }}](refresh-connection-oslogin-linux.md)
* [Удалить виртуальную машину из {{ backup-name }}](delete-vm.md)

## Управление серверами {{ baremetal-name }} в {{ backup-name }} {#connect-baremetal}

* [{#T}](backup-baremetal/backup-baremetal.md)
* [{#T}](backup-baremetal/refresh-connection.md)

## Управление политиками резервного копирования {#policy-vm}

* [Создать политику резервного копирования](./policy-vm/create.md)
* [Изменить политику резервного копирования](./policy-vm/update.md)
* [Привязать виртуальную машину к политике резервного копирования](./policy-vm/attach-and-detach-vm.md)
* [Получить информацию о политике резервного копирования](./policy-vm/get-info.md)
* [Отвязать виртуальную машину от политики резервного копирования](./policy-vm/detach-vm.md)
* [Удалить политику резервного копирования](./policy-vm/delete.md)

## Управление резервными копиями {#backup-vm}

* [Создать резервную копию виртуальной машины](./backup-vm/create.md)
* [Восстановить виртуальную машину из резервной копии](./backup-vm/recover.md)
* [Восстановить виртуальную машину из резервной копии другой виртуальной машины](./backup-vm/non-native-recovery.md)
* [Восстановить на виртуальной машине отдельные директории и файлы](./backup-vm/recover-file-by-file.md)
* [Удалить резервную копию](./backup-vm/delete.md)

## Сервисные операции {#service-operations}

* [Активировать сервис](activate-service.md)
* [Посмотреть операции с ресурсами сервиса](operation-logs.md)
* [Посмотреть статистику резервного копирования](get-stats.md)
