* `--resource-ids` — идентификаторы ваших ресурсов или ресурсов {{ yandex-cloud }}, например функций {{ sf-name }}.
* `--resource-types` — типы ресурсов, например функции {{ sf-name }} `serverless.function`.
* `--stream-names` — потоки логирования.
* `--log-levels` — уровни логирования.
  Триггер срабатывает, когда в указанную лог-группу добавляют записи, которые соответствуют всем следующим параметрам: `resource-ids`, `resource-types`, `stream-names` и `log-levels`. Если параметр не задан, триггер срабатывает при любом его значении.
  