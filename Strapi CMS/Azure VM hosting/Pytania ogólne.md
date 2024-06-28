#### Kto powinien mieć możliwość uruchamiania CMSa w celu wprowadzenia zmian? (jeśli nikt techniczny, to sposób uruchamiania do rozważenia)


Odp: 
- Opcja wygodna, nie trzeba nikogo dodatkowo angażować i daje elastyczność. 
- **ZROBIĆ RESEARCH NAD MOŻLIWOŚCIAMI OBSŁUGI VM PRZEZ OSOBĘ NIETECHNICZNĄ**



#### Jaki wariant deploymentu rozważamy? Automatycznie, manualnie?
(bez rozdzielenia na środowiska, automatycznie publikujemy od razu na produkcję?)

Odp: 


#### Czy pipeline powinien mieć możliwość uruchamiania i zatrzymywania VMki?

Odp: Tak


#### Czy jeden pipeline wystarczy?

Odp: Będzie potrzebne rozdzielenie. Rozdzielenie pipelina zmiany wersji (update obrazu) od pipelina do samego korzystania z cmsa. 
##### Także potrzebne będą zmiany w pipeline dla frontu, ponieważ za każdym razem, gdy frontend ma zostać przebudowany, musi on mieć dostęp do danych serwowanych przez CMS.


#### Czy rozdzielamy od razu środowisko na staging i production? ([Link](https://learn.microsoft.com/en-us/azure/static-web-apps/branch-environments?tabs=github-actions))
(Jest możliwość wydzielenia do 3 darmowych stage-y aplikacji frontowej. Dodatkowe stage są dostępne pod stałą domeną przypisaną przez Azure. W tym wypadku należy przygotować odpowiednio pipeliny, przygotować dodatkowy branch na GitHubie oraz odpowiednio dostosować deployment workflow na GitHubie dla Azure oraz połączyć aplikację frontową z bazą produkcyjną.)

Odp: CMS - jedno wspólne środowisko. Frontend - rozdzielamy na STAGING/PRODUCTION


#### Czy jeśli chcemy rozdzielić środowiska, to chcemy testowe ukryć za VPNem?

Odp: Na ten moment nie.



#### Co w przypadku niepowodzenia na jakimś etapie procesu? Retries, czy wyłączenie VM do czasu zdebugowania?

Odp:

  



