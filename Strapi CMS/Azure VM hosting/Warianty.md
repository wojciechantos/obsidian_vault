#### %% FULL AUTO Przy rozdzieleniu środowisk %%

Po zaakceptowaniu zmian w PR dla danej funkcjonalności i mergu do brancha main, automatycznie uruchamia się przygotowany pipeline

Przykład:

1. Uruchomienie VM na Azure poprzez Azure CLI
2. Health check VMki bez uruchamiania aplikacji
3. Zalogowanie do VMki i git pull gałęzi MAIN z repo Bitbucket w celu aktualizacji
4. Zainstalowanie, zaktualizowanie narzędzi (`yarn install`)
5. Uruchomienie `docker compose up` na VM w celu uruchomienia Strapiego sprawdzeniu czy aplikacja uruchamia się poprawnie po aktualizacji
6. Uruchomienie przebudowania aplikacji frontowej w celu aktualizacji na środowisku STAGING/DEVELOPMENT
7. Po poprawnym przebudowaniu aplikacji frontowej, wyłączenie VMki

![[AzureVM__deployment.png]]

#### %% FULL AUTO Bez rozdzielania środowisk %%

Jak powyżej z różnicą w punkcie 6. Różnica polega na przebudowaniu aplikacji frontowej na produkcyjnym środowisku  


---

#### %% Manual deployments %%

W tym wariancie mogą zostać przygotowane pipeliny, które będą odpowiadały osobno za:
- uruchomienie VM i wdrożenie zmian na Azure VM do aplikacji Strapiego
- przebudowanie aplikacji frontowej
- Jeśli rozdzielone zostaną środowiska, to także osobne pipeliny do przebudowania danego środowiska.

Tutaj każdy krok będzie musiał być wykonany manualnie, tj. uruchomienie odpowiadającego piepline'a.
