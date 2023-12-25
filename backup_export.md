## Backup -> Export
```
:local date [/system clock get date]
:local time [/system clock get time]
:set date ([:pick $date 5 11])
:set time ([:pick $time 0 2])
:local backupName ("backup" . $date . "godz" . $time)
/export file=$backupName
:log info ("Export MT: " . $backupName)
```