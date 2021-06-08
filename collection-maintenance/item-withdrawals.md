# item withdrawals

## introduction
- Through various routes specific items enter into the process of being removed from the system
- This involves removing the digital traces of the item (in the computer catalog) and the physical item (e.g. the book)
- After the decision has been made to withdraw an item, staff mark the item `STATUS`: `LIB USE ONLY` and [scan the barcode into the staff-portal](http://10.0.8.54:44423/starport-alpha/collection/ilsmaint/withdrawal)
- This begins the arm of the process to remove the digital presence of the item.
- The digital records of the items sit in a period of status, where they are `LIB USE ONLY` but the records still exist in the catalog.
- After that period of status (right now, 10 days), to make sure no "take-backs" are in order, the digital records are deleted, and certain information is transferred to a local database.

## identify records to delete
- At any given time, any items eligible for withdrawal in this process can be found on the [Withdrawals: Deletions page on the staff-portal](http://10.0.8.54/staff-portal/ilsmaint/withdrawal/deletions)
  - This page displays a list of item record keys from which one can create a `Review File` in Sierra. [Information regarding that process can be found here](https://github.com/jmrlibrary/collspec-tasks/wiki/Create-a-Review-File-from-a-list-of-item-reckeys)

## export data to retain

### export a `.csv` file
- Export the `Review File` created above using the orange `[Export Records`] button 
  - in the dialog box, click `[Apply Saved Export]` and choose `collection specialist - withdrawals` and click ok
  - in the (same) dialog box, click `[Browse`] and choose a filename and file destination. 
    - **make sure to end the filename with `.csv` so it can be easily opened by spreadsheet programs.

### export `.out` file
- Exporting of `marc` records (by convention in this case using a `.out` extension) is sometimes done in the case of bulk deletions or record changes, in case Cataloguing needs access to those records after the face. However, due to the numerous safeguards which are being put in place with item withdrawal deletions, this is becoming redundant. Check with your supervisor?
- Export marc records of files with Data Exchange
- In `FUNCTION -> Data Exchange` from the `Select process` dropdown choose `Output MARC records (out)`.
- Click the icon on the upper right `CREATE file of BIB, AUTHORITY, OR ITEM records`.
  - Choose name for the output file
  - Select your Review File from the dropdown menu
  - Click 'Start`
  - When the process is done, click `Close` (upper right) to return to the main Data Exchange screen
- Locate and click on your file (you can sort by `last modified`) 
- Click `Download to PC` (upper right)
- Download it and retain it until the next time you complete this process.

## delete digital records
- Using `Delete Records`, delete the contents of the Review File. 
  - You **may** use option `Delete the listed ITEM record AND attached BIBLIOGRAPHIC record (if no other records attached)`

## save retained data to local database
- [TODO]

## if you encounter problems:
