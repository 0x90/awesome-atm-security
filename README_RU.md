# Безопасность банкоматов

## Метериалы для чтения

### Антивирусные материалы

https://securelist.com/atmii-a-small-but-effective-atm-robber/82707/

https://blog.trendmicro.com/trendlabs-security-intelligence/alice-lightweight-compact-no-nonsense-atm-malware/

https://documents.trendmicro.com/assets/appendix-alice-lightweight-compact-atm-malware-2.pdf

https://github.com/threatrack/cti_report_collection/blob/master/text/20190821-groupib-silence2_0.txt

https://github.com/eyalmazuz/ThreatIntelligenceCorpus/blob/master/Corpus/securityaffairs_atm-skimer-malware.html.txt

### Доклады на тему безопасности банкоматов

http://dc7495.org/aybbtu/uploads/2019/01/DC7495-Banks.pdf

https://www.ptsecurity.com/upload/corporate/ru-ru/analytics/ATM-Security-rus.pdf

https://www.ptsecurity.com/upload/corporate/ww-en/analytics/ATM-Vulnerabilities-2018-eng.pdf

### Примеры уязвимостей  

CVE-2018-5717, CVE-2017-17668

https://www.rewterz.com/threats/flaws-in-atm-dispenser-controllers-allowed-hackers-to-steal-cash

https://www.ncr.com/content/dam/ncrcom/content-type/case_studies/ncr_security_alert_-_2018-04_v3.pdf

https://www.ncr.com/content/dam/ncrcom/content-type/documents/NCR_Security_Alert-2018-13_APTRA_XFS_v5.pdf

https://www.ncr.com/content/dam/ncrcom/content-type/brochures/17fin5025_a_sec_rqts_protect_logical_attacks_wp.pdf

http://images.response.ncr.com/Web/NCRGlobal/%7B18bc5b2d-2bbb-4016-be87-33043d92d17c%7D_FIN_Security_Alerts_Currency_Dispenser_WP_091218.pdf

[Подобная уязвимость открыта но в 2012 году?](http://bankomatchik.ru/forums/topic?f=52&t=2824&view=print)

https://i.blackhat.com/us-18/Thu-August-9/us-18-Stennikov-Blackbox-is-dead--Long-live-Blackbox!.pdf


### Jackpoing

https://github.com/fboldewin/ATM-Jackpotting-P4WNP1-style-with-malware-XFS_DIRECT

https://github.com/marcacohen/notes/blob/master/articles/First%20%E2%80%98Jackpotting%E2%80%99%20Attacks%20Hit%20U.S.%20ATMs%20%E2%80%94%20Krebs%20on%20Security.md

###  Список ссылок

[Банкоматчик  WiKi](http://bankomatchik.ru/wiki/ncr:aptra)


https://www.ptsecurity.com/ru-ru/research/analytics/atm-vulnerabilities-2018/

https://www.slideshare.net/codeblue_jp/cb16-kochetova-en

https://www.slideshare.net/PacSecJP/kochetovaosipv-atm-howtomakethefraudfinal
https://www.slideshare.net/KasperskyLabGlobal/live-in-the-atm-trenches

Аналитика от PBF Group. Атаки типа Black Box на устройства финансового самообслуживания.
https://www.pbfgroup.ru/news/detail.php?ID=49

Система контроля SDC-шины / USB
https://www.pbfgroup.ru/solutions/sistema-kontrolya-sdc-shiny-usb/

Система ограничения доступа к сервисной части банкомата
https://www.pbfgroup.ru/solutions/stopskimmer-controller-atm-advanced-standart/


https://docplayer.net/49410621-Atmdesk-repair-diagnostic-solution-for-ncr-56xx-58xx-personas-53xx-easypoint-66xx-selfserv-atms-installation-manual-version-8.html


https://www.walmart.com/ip/RS232-to-RS485-Communication-Data-Converter-Adapter-for-ATM-Machine/46019113
https://www.priceza.com/s/%E0%B8%A3%E0%B8%B2%E0%B8%84%E0%B8%B2/rs-232-to-rs-485-interface-converter


https://gcsec.org/wp-content/uploads/2016/09/future-atm-threat-landscape-attack-scenarios-against-authentication-system-communicating-with-atm_kaspersky_001.pdf

https://rkelectronics.ru/antiblek-boks/

https://popovsg.ucoz.ru/load/atm/kljuchevaja_disketa_dlja_poluchenija_dstupa_k_polnomu_menju_aptra/2-1-0-4


### Доступ к полному меню APTRA


Такой проблемы нет у тех инженеров, которые имеют в распоряжении официальный ключ. Всем же прочим нужно искать обходные пути. Здесь описан способ с применением ключевой дискеты (3.5").

Прежде всего - надо достать дискету. В интернете есть в относительно свободном доступе несколько образов, например на сайте http://bankomatchik.ru/forum/index.php. А можно договориться с обладателем легальной дискеты - кому как удобней.

На "старых" банкоматах, в системном блоке которых установлена материнская плата PELE II, этого будет достаточно. Запускаем APTRA, предварительно вставив дискету, вводим PIN, работаем. Для банкоматов, которые основаны на PIVAT, требуется совершить небольшой шаманский обряд.

Войдя в Windows с правами администратора системы, нужно прогрузить файл 5870bios.reg, данный файл "подменяет" в реестре версию биос. На работоспособность системы в целом это никак не влияет, но следует помнить, что внесённые изменения действуют ТОЛЬКО ДО ПЕРЕЗАГРУЗКИ Windows.

Далее - запускаем APTRA, предварительно не забыв вставить в дисковод ключевую дискету (впрочем, она уже вставлена - подразумевается, что 5870bios.reg записан на ней) или... изготовленную самостоятельно ключевую флешку.

Участник форума (http://bankomatchik.ru/forum) SN66 подметил такую особенность: если указанный выше reg-файл загрузить с usb-flash, то APTRA при старте будет опрашивать на предмет сервисного ключа именно usb-flash, а не дискету. Таким образом, имеющуюся в наличии ключевую дискету копируем на флешку (вместе с 5870bios.reg), прогружаем с неё reg-файл, запускаем APTRA.

Справедливости ради, способ от SN66 работает не всегда. Я не задавался целью выяснить, какая версия APTRA стояла на банкоматах, где это не сработало (не было насущной необходимости). Участник того же форума kentaur7777 отметил, что у него не получилось воспользоваться таким способом на банкоматах SelfServ, APTRA 3.4.1 (http://bankomatchik.ru/forum/viewtopic.php?f=2&t=26#p8464).

Ссылки на файл 5870bios.reg:

1. http://bankomatchik.ru/forum/download/file.php?id=28

2. http://popovsg.ucoz.ru/load/atm/5870bios_reg/2-1-0-5

Полный текст статьи: http://popovsg.ucoz.ru/load/atm/dostup_k_polnomu_menju_aptra/2-1-0-8

08.01.2011

Sergey G. Popov


http://bankomatchik.ru/wiki/

## Код по теме

### XFS SDK 3

ftp://ftp.cenorm.be/CWA/CEN/WS-XFS/SDK%20XFS3

### XFS API 2

https://github.com/bigcool/freexfs


### Примеры работы с XFS API

https://github.com/Mingun/pcsc-cenxfs-bridge

https://github.com/mortezabarzkar/XFS4NET

https://github.com/andysinenko/XFSPrint

https://github.com/Joker2770/XFStool


### Blackbox и попытка защиты

https://github.com/FernandoZnga/blackbox-frontend

https://github.com/FernandoZnga/blackbox-backend

https://github.com/meladark/SecLoRaATM


### Антималварные инструменты

https://github.com/vallejocc/PoC-Fake-Msxfs

https://github.com/fireeye/capa

https://github.com/fireeye/capa-rules/tree/master/targeting/automated-teller-machine

###

[APTRA NDC симулятор](https://github.com/timgabets/electron-atm)

Тестирование безопасности с помощью симуляции

https://iso8583.info/


Contactless test cards simulation tool
https://iso8583.info/hcebridge/


https://iso8583.info/about/




* [ATMSERVICES GMBH - ATMdesk](https://www.atm-services.de/ru/products/atmdesk-keys/)
* [Альтернативная флешка для доступа к диагностике - Страница 2 из 4](http://bankomatchik.ru/forums/45/213?start=20)
* [Альтернативная флешка для доступа к диагностике](http://bankomatchik.ru/forums/45/213)
* [Роутеры iRZ в банковской сфере - Блоги](http://bankomatchik.ru/blogs/routery-irz-v-bankovskoj-sfere)
* [MiddleEast Tech. by GulenTech Group ATM Parts of NCR,Diebold and Wincor e-mail : sales@middleeasttech-cn.com.com](http://www.middleeasttech-cn.com/indeks.php?sid=41&lang=2)
* [Диагностика без USB ключа. - Страница 2 из 2](http://bankomatchik.ru/forums/2/26?start=20)

