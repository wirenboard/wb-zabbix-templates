# wb-zabbix-templates

Wiren Board device templates for Zabbix.

Готовые шаблоны Zabbix для мониторинга устройств Wiren Board по MQTT через Zabbix Agent 2.

## Что внутри

- `templates/` — готовые Zabbix-шаблоны по моделям устройств WB (YAML, формат импорта Zabbix 7.0).

## Требования

- Zabbix 7.0 LTS или новее.
- Zabbix Agent 2 со встроенным MQTT-плагином (рекомендуется 7.0.10+ / 6.0.39+).
- Сетевой доступ от агента к MQTT-брокеру контроллера Wiren Board.

## Как использовать

1. Импортируйте YAML нужной модели из `templates/` (Data collection → Templates → Import).
2. Создайте хост, привяжите шаблон. Имя хоста должно совпадать с `Hostname` агента.
3. Задайте макросы `{$MQTT.BROKER}` (адрес брокера контроллера) и `{$DEVICE}` (slug `<модель>_<slave_id>`, например `wb-mr6cu_23`).
4. Значения появятся в Monitoring → Latest data.

[Подробная инструкция на вики](https://wiki.wirenboard.com/wiki/Шаблоны_Zabbix_для_устройств_Wiren_Board).

## Лицензия

MIT (см. [LICENSE](LICENSE)).
