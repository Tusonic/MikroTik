## Backup MikroTik Export and Send To Mail
```
:local date [/system clock get date]
:local time [/system clock get time]
:set date ([:pick $date 5 11])
:set time ([:pick $time 0 2])
:local backupName ("backup" . $date . "godz" . $time)
/export file=$backupName
:local emailTo "name@example.mail"
:local emailSubject ("backup mt nap - " . $date . " " . $time)
:local emailBody "backup mt nap"
/tool e-mail send to=$emailTo subject=$emailSubject body=$emailBody file=($backupName . ".rsc")
```