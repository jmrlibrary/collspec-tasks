# tasks

## irregular

### loading Overdrive electronic records
- **When** Upon receiving email from Collection Manager (weekly?)
- Process
  - download files locally
  - use `Data Exchange` to load files
  - copy into a `Review File`
  - use `Global Update` to process the `Review File` with the proper `load profile`
  - done!

## daily

## weekly

### suppress items that can't circulate
- a list of item record numbers which can be suppressed is generated programmatically on the Staff-Portal `http://10.0.8.54/staff-portal/collection/ilsmaint/items/suppressible`. 
- these are determined by identifying any items with `icode2 != 'n'` with their last known record update to their current suppressible status condition `('m', 'z', '$', 'n')` (missing, claims returned, lost and paid, billed) having occurred one year or more ago. this is double-checked against circulation within the last year (in a separate search to change item status condition for items that have been circulating but have a status code indicating otherwise) . 
- maintainers can :
  - copy this list
  - create a Review File of Items from these record numbers (See wiki for documentation)
  - examine the contents of the Review File in `Global Update` or using other `Review Files` : filter out any items which look like they are appearing erroneously
  - suppress the records (changed `item status code` to `n`) using `Rapid Update`
  - done.

## twice a month

### item withdrawals 
- **When:** Whenever you want, as long as it's once per fortnight.
- [Documentation](https://github.com/jmrlibrary/collspec-tasks/wiki/item-withdrawals)

### baker taylor 'Continuation Backorder' and 'Cancellations' report
- **When:** After receiving fortnightly email from Amanda Wilson <amanda.wilson@baker-taylor.com>
- [Documentation](https://github.com/jmrlibrary/collspec-tasks/wiki/handling-'Continuation-Backorder'-and-'Cancellations'-report-from-Baker-&-Taylor)

## monthly

### New Arrivals
- **When:** 15th of the month
- [Documentation](https://github.com/jmrlibrary/collspec-tasks/wiki/New-Arrivals-(Featured-Lists))
- Note: Both `New Arrivals` and `New Arrivals Digital` saved searches now available in `Create Lists`.

### Freading records
- **When:** After receiving email from Margaret Moore <mmoore@dgiinc.com> on or about the middle of the month.
- [Documentation](https://github.com/jmrlibrary/collspec-tasks/wiki/Freading-records)
- Tasks: 
  - Upload incoming Freading records
  - Delete inaccessible records

### Patron Suggestion record retention policy
- According to Record Retention policy, data pertaining to specific patron suggestions should be deleted one calendar year after the suggestion is received, assuming it has been closed.
- This data currently exists in five places, which makes this a bit difficult:
  - as "responses" in the google form (https://docs.google.com/forms/d/1_COTxwUK_3KYWMIDmJ4EHq119AatPGQ0krwXr2Y9m50/edit#responses)
    - I am not sure how to delete only some of these
  - as spreadsheet rows in the google sheet linked to the form: https://docs.google.com/spreadsheets/d/13LMPmqXba44L8PL2GhejUOGOQ5Ovs-31H65D_Yd__94/edit#gid=562490763
    - these currently have to be manually deleted. you must select all rows with a timestamp older than a year ago, right click, and use `Delete Rows`. Merely deleting the contents will mess up the index that the form link uses and the data will start overwriting itself or leave blank rows
  - in the `suggestions` table in the `collection` database on Scooter
    - this data is programmatically deleted each night and statistical data retained in the `collection_schema.suggestion_archive` table in the `collection` database
  - in any backups of the `collection` database (currently exorted daily to `/home/collspec/postgres/dumps/collection.db` and saved for a month)
    - deleted programmatically each day if they are older than one month, using collspec's `crontab` (version controlled in another repo here)
  - on whatever server is used to back up Scooter (because those backups are saved to their during a Scooter backup)

