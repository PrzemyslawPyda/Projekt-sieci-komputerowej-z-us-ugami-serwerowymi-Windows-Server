# Projekt sieci komputerowej z usługami serwerowymi Windows Server
Praca inżynierska będąca elementem finalizującym studia inżynierskie na kierunku Informatyka na wydziale Matematyki, Fizyki i Informatyki Uniwersytetu Opolskiego.
Obrona odbyła się w dniu 21.02.2023. 


## Projekt logiczny sieci:
![TOPOLOGIA](https://user-images.githubusercontent.com/125144567/218270789-888a821a-a55a-4b2a-9279-4c605b59eefc.JPG)

Kompletne cele i założenia pracy jak i późniejsze ich projektowanie, wdrożenie i testowanie znajduje się w pliku [Pyda_PrzemysławKrzysztof_2023.pdf.](https://github.com/PrzemyslawPyda/Projekt-sieci-komputerowej-z-uslugami-serwerowymi-Windows-Server/blob/f0b2a6fb44f7c84c84460cd58c711a9355871f8a/Pyda_Przemys%C5%82awKrzysztof_2023.pdf)
Konfiguracja urządzeń sieciowych Cisco znajduje się w pliku archiwum [KonfiguracjaUrzadzenSieciowych.zip](https://github.com/PrzemyslawPyda/Projekt-sieci-komputerowej-z-uslugami-serwerowymi-Windows-Server/blob/f0b2a6fb44f7c84c84460cd58c711a9355871f8a/KonfiguracjaUrzadzenSieciowych.zip)

## Streszczenie
Niniejsza praca dyplomowa dotyczy opracowania i wdrożenia projektu na rzeczywistych urządzeniach sieciowych klasy korporacyjnej. Praca dedykowana jest
dla małej firmy informatycznej, specjalizującej się w wytwarzaniu oprogramowania oraz projektów graficznych. Projekt zostanie zrealizowany na fizycznych
urządzeniach sieciowych firmy Cisco oraz na wirtualnym serwerze Windows Server 2016. Sieć powinna zapewnić niezawodny dostęp do programów i zasobów sprzętowych.
Niezawodność infrastruktury sieci realizowana będzie poprzez skalowalność i redundancję, co w przyszłości przyczyni się do łatwej jej rozbudowy.  

## Cele i założenia
### Założenia ogólne
- Ilość pracowników poszczególnych działów może wzrosnąć w miarę rozwoju firmy, dlatego zagospodarowanie budynku powinno zakładać możliwość zwiększenia pracowników. Dodatkowo pomieszczenia pracownicze posiadają odpowiednio większą kubaturę w celu przyszłej rozbudowy stanowisk pracy;
- Sieć powinna być w pełni skalowalna oraz redundantna. Za wszelką cenę powinno
się unikać punktów „single point of failure”, czyli pojedynczych punktów awarii, wpływających krytycznie na działanie całej sieci;
- Sprzęt serwerowy, zarówno w serwerowni jak i szafie rack podwieszanej na piętrze, powinien być niedostępny dla osób nieuprawnionych;
- Główna szafa serwerowo-sieciowa znajduje się w klimatyzowanej serwerowni. Infrastruktura powinna być odporna na chwilowe zaniki prądu.
-	Do specjalnego komputera, przeznaczonego do awaryjnego administrowania siecią komputerową możliwość logowania powinni mieć jedynie uprawnieni administratorzy. Komputer znajduje się w serwerowni.

### Założenia Windows Server
-	Użytkownicy posiadają własne konta w domenie CyberCode.com;
-	Użytkownicy synchronizują swoje pliki przy użyciu profili mobilnych z dyskiem podłączonym pod serwer w celu synchronizacji plików pomiędzy urządzeniami;
-	Użytkownicy mają narzuconą politykę tworzenia bezpiecznych haseł – minimum
10 znaków, hasło spełnia wymogi złożoności, 24 ostatnio użyte hasła są zapisywane;
-	Użytkownik przy pierwszym logowaniu będzie musiał zmienić domyślne hasło
na unikalne;
-	Odpowiednie działy posiadają odpowiednio zmapowane dyski sieciowe – według założonych uprawnień i potrzeb;
-	Serwer powinien posiadać 2 karty sieciowe działające w trybie NIC Teaming Mode;
-	Serwery powinny działać redundantnie i przejmować kluczowe usługi takie jak Active Directory czy role serwera DHCP w wypadku awarii jednego z dwóch serwerów;
-	Użytkownicy powinni mieć dostęp do intranetu i dwóch stron dostępnych
dla wszystkich autoryzowanych użytkowników – strona informacyjna cybercode.local oraz portal pracowniczy portal.cybercode.local;
-	Administracja warstwy serwerowej powinna w razie możliwości być prowadzona
w języku angielskim.

### Założenia sieciowe
-	Pracownicy poszczególnych działów grupowani są w odpowiadające sobie sieci VLAN (Virtual LAN) w celu logicznego odseparowania od innych działów;
-	Użytkownicy nie mogą przynosić swoich urządzeń bez wiedzy administratora;
-	Użytkownicy nie będą łączyć się zdalnie, poprzez VPN, do zasobów sieci firmowej;
-	Poszczególne sieci VLAN powinny mieć dostęp do serwerów DHCP. Nie powinno zachodzić wycinanie ruchu rozgłoszeniowego potrzebnego do otrzymania automatycznej adresacji IPv4;
-	Administratorzy powinni mieć dostęp do urządzeń sieciowych przy pomocy szyfrowanego połączenia SSH po poprawnym procesie autoryzacji.

## Technologie
W pracy inżynierskiej wykorzystano protokoły i technologie będące w zdecydowanej większości w zakresie certyfikacji CCNA. W projekcie od strony sieciowej wykorzystano m.in. GLBP, Rapid-PVST, OSPF, DHCP Snooping, DAI, sieci VLAN czy Inter-VLAN routing via L3 Switches, zaś od strony Windows Server 2016 wykorzystano m. in. redundantne AD, fail-over DHCP, serwer stron IIS, automatyczne mapowanie odpowiednich dysków sieciowych czy też zdalne wdrażanie oprogramowania Google Chrome z dedykowaną konfiguracją ADM poprzez obiekty GPO.

## Bezpieczeństwo infrastruktury
Bezpieczeństwo infrastruktury zostało opisane na stronach 77-79 i zostało podzielone na 4 sekcje:
- Bezpieczeństwo budynku
- Bezpieczeństwo dostępu administracyjnego
- Bezpieczeństwo sieciowe
- Bezpieczeństwo Windows Server

## Podsumowanie
Przez cały tok realizacji pracy inżynierskiej autor poszerzył swoje umiejętności praktyczne
oraz poznał nowe protokoły i mechanizmy wykorzystywane w sieciach komputerowych.
Cel pracy został osiągnięty. Oczywiście, projekt można dalej rozwijać. Pomysłami, które można by wdrożyć
jest wykorzystanie PAT (Port Adress Translation), wdrożenie środowiska do monitorowania sieci (np. LibreNMS, GrayLog) oraz utworzenie klastrów Windows Server, aby zwiększyć odporność na awarię. Idąc dalej – można wdrożyć zapory ogniowe Firewall, zarówno typu sprzętowego, jak FortiGate 200F czy Cisco ISA albo oprogramowanie, np. OPNsense. W przypadku realnego rozwoju infrastruktury logicznym, narzucającym się krokiem jest wdrożenie połączeń bezprzewodowych przy użyciu kontrolera WLC oraz punktów AP.

