# BehovsBoBoxen är ett styrsystem för smarta hem baserad på Raspberry Pi.
![detta behöver du](http://www.behovsbo.se/themes/images/bbbmaterial.jpg)

Bom | Materiallista
--- | -------------
1 | 1 Raspberry pi 2 eller 3 modell B
2 | 8 ds18b20 med pinnar
3 | 1 ds18b20 vattensäker
4 | 1 micro SD kort 8GB
5 | 1 reläkort med 8 relän
6 | 1 5V 2,1A USB laddare
7 | 1 kopplingsdeck
8 | 1 knippe kopplingssladdar hane-hane
9 | 1 knippe kopplingssladdar hona-hona
10 | 1 Ethernetsladd


1. Koppla in temperaturgivarna (ds18b20) med plus, minus och signal på GPIO4. Systemet är byggt för 8 rum samt en utegivare.

2. Reläkortet kopplas med sina 8 relän från GPIO pinnarna som är angivet i samma ordning som anges i början av filen `/home/pi/behovsboboxen/scripts/dallas.py`

3. Normal läge för IP adress är DHCP. Man kan, om så önskas, låsa sin ip-adress via routern.

4. Om du vill kunna nå BehovsBoBoxen från Internet måste du göra en portvidarebefodran i er router, se manualen hur det görs.

5. Du har laddat ner och installerat Raspian från `https://www.raspberrypi.org/downloads/noobs/` och konfigurerat till svenska förhållanden.

6. Ladda nu ner den senaste versionen från vår katalog (repository) med git klienten `git clone https://github.com/Electrotest/BehovsBoBoxen`

7. Kör installationsskriptet och följ de givna instruktionerna `sudo sh /home/pi/BehovsBoBoxen/behovsboboxen/scripts/install.sh`

8. Nu kan du gå in på `https://your.ip.n.r` Logga in med root:root. Första gången kan du få en varning och få klicka för att du litar på certifikatet. Det är ju bara signerat av dig och inte någon professionell Certificate Authority, CA.
Boxen kan även hittas med adressen `https://behovsboboxen`. Vill du inte använda certifikatet utelämnar du s och skriver http.

9. Du byter namn och lösenord på administrationssidan. Om du glömmer inloggningsuppgifterna kan du installera om Boxen – ingen större skada skedd.

10. Om 1-wire sensorer är inkopplade enligt anvisningen, skall det med sökvägen `/sys/bus/w1/devices` finnas mappar där varje sensor anger sin temperatur. Öppna respektive mapp och öppna filen w1_slave. Där finns temperaturen, t.ex. t=21062. Dividera med 1000 så får du temperaturen i grader celcius.

11. Reläna skall kopplas med dupontsladdar enligt pin-konfigurationen i `/home/pi/behovsboboxen/scripts/dallas.py`. Kom också ihåg att koppla 5 volt plus och gnd.

12. Rundstyrning (DSM) kan användas om man gör ett avtal med sitt elnätsbolag om att styra laster för att förhindra störningar på det lokala elnätet.



#### The interface of Behovsboboxen is based on Lydia, which is a PHP-based, MVC-inspired CMF

You find Lydia here: [Lydia](https://github.com/mosbth/lydia)

The modified and accustomed version is made by Gunvor Nilsson.


#### License

Behovsboboxen (and Lydia) is licensed according to MIT-license. 


[License/ Pricing:](http://canvasjs.com/download-html5-charting-graphing-library/)
> CanvasJS is free for non-commercial and paid for commercial use.