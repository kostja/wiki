# Picodata Releases 25.3.5 — 25.3.7

## [25.3.5] - 2025-10-03

Улучшения, исправления:

- Instance's which loose ability to apply raft log updates will automatically become Offline.
  [#2238](https://git.picodata.io/core/picodata/-/issues/2238)

- New ALTER SYSTEM parameter `plugin_check_migration_hash` (default: true) allows disabling plugin migration file checksum validation. This allows plugin authors to more easily fix mistakes in migration files.
  [не найден; docs follow-up: #2259](https://git.picodata.io/core/picodata/-/issues/2259)

- Fixed bizarre row order produced by ORDER BY \<uuid\>.
  [#2217](https://git.picodata.io/core/picodata/-/issues/2217)

- Fixed a possible state corruption in case picodata crashes after receiving a raft snapshot with a stale schema version.
  [не найден]

- Fixed TRUNCATE operation for global tables.
  [#2274](https://git.picodata.io/core/picodata/-/issues/2274)

## [25.3.6] - 2025-10-10

- Fix compilation error on ARM architecture.
  [не найден]

- Fix erroneous ER_READONLY message in logs when executing TRUNCATE on global tables.
  [#2274](https://git.picodata.io/core/picodata/-/issues/2274)

## [25.3.7] - 2025-10-16

- Fix Service::on_leader_change callbacks not being called after master goes Offline due to sentinel auto-offline policy.
  [#2303](https://git.picodata.io/core/picodata/-/issues/2303)

- Add IF NOT EXISTS support for ALTER TABLE ADD COLUMN.
  [#2208](https://git.picodata.io/core/picodata/-/issues/2208)
