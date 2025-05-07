## BACKUP SCRIPTS (MT 7.18.2)

```
:local date [/system clock get date]
:local time [/system clock get time]
:local dateTime ([:pick $date 0 4] . [:pick $date 5 7] . [:pick $date 8 10] . "_" . [:pick $time 0 2] . [:pick $time 3 5])

:local fileExport "backup_$dateTime.rsc"
:local fileExportVerbose "backupV_$dateTime.rsc"
:local fileBackup "backup_$dateTime.backup"

/export show-sensitive file=$fileExport
:delay 5
/export verbose show-sensitive file=$fileExportVerbose
:delay 5
/system backup save name=$fileBackup

 ```