РЕЛИЗ
[25.3.5] - 2025-10-03
Улучшения, исправления

| Описание | Перевод | Ссылки |
|----------|---------|--------|
| Instance's which loose ability to apply raft log updates will automatically become Offline. | Экземпляры, потерявшие возможность применять обновления журналов Raft, автоматически перейдут в автономный режим. | https://git.picodata.io/core/picodata/-/issues/2238 |
| New ALTER SYSTEM parameter `plugin_check_migration_hash` (default: true) allows disabling plugin migration file checksum validation. This allows plugin authors to more easily fix mistakes in migration files. | Новый параметр ALTER SYSTEM `plugin_check_migration_hash` (по умолчанию: true) позволяет отключить проверку контрольной суммы файлов миграции плагинов. Это позволяет авторам плагинов проще исправлять ошибки в файлах миграции. | не найден (docs: https://git.picodata.io/core/picodata/-/issues/2259) |
| Fixed bizarre row order produced by ORDER BY <uuid> | Исправлена странная последовательность строк, создаваемая оператором ORDER BY <uuid>. | https://git.picodata.io/core/picodata/-/issues/2217 |
| Fixed a possible state corruption in case picodata crashes after receiving a raft snapshot with a stale schema version. | Исправлена возможная ошибка искажения состояния в случае сбоя picodata после получения снимка Raft с устаревшей версией схемы. | не найден |
| Fixed TRUNCATE operation for global tables. | Исправлена операция TRUNCATE для глобальных таблиц. | https://git.picodata.io/core/picodata/-/issues/2274 |

РЕЛИЗ
[25.3.6] - 2025-10-10

| Описание | Перевод | Ссылки |
|----------|---------|--------|
| Fix compilation error on ARM architecture. | Исправлена ошибка компиляции на архитектуре ARM. | не найден |
| Fix erroneous ER_READONLY message in logs when executing TRUNCATE on global tables. | Исправлена ошибка, из-за которой в логах иногда появлялось ошибочное сообщение ER_READONLY при выполнении команды TRUNCATE для глобальных таблиц. | https://git.picodata.io/core/picodata/-/issues/2274 |

РЕЛИЗ
[25.3.7] - 2025-10-16

| Описание | Перевод | Ссылки |
|----------|---------|--------|
| Fix Service::on_leader_change callbacks not being called after master goes Offline due to sentinel auto-offline policy. | Исправлена ошибка, из-за которой коллбэки Service::on_leader_change не вызывались после перехода основного сервера в автономный режим из-за политики автоматического отключения Sentinel. | https://git.picodata.io/core/picodata/-/issues/2303 |
| Add IF NOT EXISTS support for ALTER TABLE ADD COLUMN. | Добавлена поддержка условия IF NOT EXISTS для команды ALTER TABLE ADD COLUMN. (Функционал изначально был необходим, но был упущен в разработке.) | https://git.picodata.io/core/picodata/-/issues/2208 |
