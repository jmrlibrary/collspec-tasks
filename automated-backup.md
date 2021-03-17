# backing up and maintaining backups for postgres databases

- folder with `.sh` scripts: `/home/collspec/bin/pg-backup`

## create directory backups daily

each database has separate script.
run from cron:
```cron
       ####
      # BACKUPS
      ####
      #      backup postgres 'hr' database
      @daily /home/collspec/bin/pg-backup/pg-dump-hr.sh
      #       backup postgres 'collection' database
      @daily /home/collspec/bin/pg-backup/pg-dump-collection.sh
      #       backup postgres 'auth' database
      @daily /home/collspec/bin/pg-backup-pg-dump-auth.sh
```
## vacuum databases
- only collection and hr
- filepath: `~/bin/postgres/maintenance/vacuum-log.sh`
- logged (just indication of completion) to `~/logs/postgres-maintenance/index.log`


## deleting old backups weekly
- filepath: `~/bin/postgres/backup/delete-old-backups.sh`
- deletes pg_dump dirs that are a month or more old (since last modification)

