## WIFI PASSWORD RANDOM (wifi wave2)
```
:local new ([/tool fetch url="https://www.random.org/passwords/?num=1&len=10&format=plain&rnd=new" output=user as-value]->"data")
:local emailTo "name@example.mail"
:local emailSubject "new password"
:local emailBody "$new"
:log info $new
/interface wifiwave2 security set [find name=secure] passphrase=$new
/tool e-mail send to=$emailTo subject=$emailSubject body=$emailBody
```