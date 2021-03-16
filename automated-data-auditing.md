# automated data auditing

## `crontab`
- Scooter runs `cron` events (currently repod at https://github.com/jmrlib/collspec-crontab)
- Some of these add, transfer, or modify information to one or more postgres databases running on scooter
- These databases are accessed by the `staff-portal` and their utility stops there
- Below are enumerated the tasks, all of which are run at least daily
- For the most part they are in the `sprint-server` repo at `/src/data-auditing`

### auth status updating

### google drive transfer
[Suggest a Purchase Spreadsheet](https://docs.google.com/spreadsheets/d/13LMPmqXba44L8PL2GhejUOGOQ5Ovs-31H65D_Yd__94)

### item code audit

### circ trans data audit

