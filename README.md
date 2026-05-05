# CI3 Backup Tools

Composer package for CodeIgniter 3 projects to backup and restore:

- database dump
- `uploads/` folder

## Install

### Option A: local/VCS install

```bash
composer config repositories.ci3-backup-tools path packages/ci3-backup-tools
composer require alihsaan/ci3-backup-tools:@dev
```

### Option B: Packagist

After publishing:

```bash
composer require alihsaan/ci3-backup-tools
```

## Commands

From your project root:

```bash
vendor/bin/ci3-backup
vendor/bin/ci3-restore /absolute/path/to/ci3-backup_YYYY-mm-dd_HH-MM-SS.tar.gz
```

You can pass a target app directory too:

```bash
vendor/bin/ci3-backup /var/www/html/another-ci3-app
vendor/bin/ci3-restore /path/to/backup.tar.gz /var/www/html/another-ci3-app
```

## Config

By default, config is loaded from `<APP_DIR>/.env`.
Copy `.env.sample` from this package and set DB + remote settings.

Main keys:

- `DB_HOST`, `DB_PORT`, `DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD`
- `REMOTE_BACKUP_MODE=none|rsync|ftp`
- `REMOTE_KEEP_LOCAL=true|false`
- `VERIFY_BACKUP=true|false`

## Publish package

1. Push `packages/ci3-backup-tools` to its own GitHub repository
2. Keep `composer.json` as package root
3. Tag release (e.g. `v1.0.0`)
4. Submit repository on [Packagist](https://packagist.org/)
