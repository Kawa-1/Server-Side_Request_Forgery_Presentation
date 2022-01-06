#Jak zintegrować Burp z przeglądarką, aby wykonać ćwiczenia?
<ul>
<li>Można się posłużyć instrukcją z labów: https://github.com/djuszka/BAWiM_lab_2021/blob/main/BAWiM_lab2.md#user-content-zadanie-2-konfiguracja-przegl%C4%85darki</li>
<li>Albo skorzystać z przeglądarki wbudowanej w burpa: proxy -> Open browser. Teraz podając adres url do przeglądarki można przystąpić do wykonywania zadań.</li>
</ul>


<h1>Zadania</h1>

## Zadanie 1
W tym zadaniu podobnie jak w każdym kolejnym będziemy musieli usunąć użytkownika Carlos. W tym celu trzeba dostać się do panelu admina.  

<details>
<summary>Wskazówki</summary>

* W narzędziu Burp przyjrzyj się dokładnie Requestowi, który jest wysyłany po naciśnięciu przycisku "Check Stock".
* W ćwiczeniu warto wykorzystywać burpRepeater.

</details>

link: https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-localhost?fbclid=IwAR0dH7pc6GHqp6rqRj7nd0xpDWlrtvbTEIFlJZ-sQOPA134sh8pMOpgkqZo

## Zadanie 2
Tym razem twórca strony zaimplementował filtr Whitelist, aby zabezpieczyć stronę przed atakami SSRF. Znajdź sposób jak obejść te zabezpieczenia.

<details>
<summary>Wskazówki</summary>

* Sprawdź, jaka będzie odpowiedź serwera, jeśli spróbujesz wykonać te same czynności co w zadaniu poprzednim.
* Do skutecznego ominięcia Whitelisty konieczne jest zmanipulowanie portem, dodanie @ do adresu oraz podwójnie zakodowanego znaku #.

</details>

link: https://portswigger.net/web-security/ssrf/lab-ssrf-with-whitelist-filter?fbclid=IwAR1ZAf9wsAgtq6iMbuS-9nHyGL3ISnkPja2vIiPaR3-ily_xKAmwACaU2RQ

## Zadanie 3
Zadanie łatwiejsze od poprzedniego, ponieważ programista zaimplementował filtr typu blacklist.

<details>
<summary>Wskazówki</summary>

* Wróć do prezentacji i sprawdź, jak można inaczej zapisać adres 127.0.0.1. Sprawdź jakie odpowiedzi zwraca serwer i wybierz odpowiednią metodę.
* Sprawdź, czy teraz możesz przejść do panelu admina. Jeśli nie -> spróbuj ponownie wykorzystać double URL encoding.

</details>

link: https://portswigger.net/web-security/ssrf/lab-ssrf-with-blacklist-filter?fbclid=IwAR0dH7pc6GHqp6rqRj7nd0xpDWlrtvbTEIFlJZ-sQOPA134sh8pMOpgkqZo

## Zadanie 4
Wykorzystaj endpoint do usuwania użytkowników, który jest zlokalizowany na innej instancji.

<details>
<summary>Wskazówki</summary>

* Skorzystaj z burpIntrudera, aby zbadać odpowiedzi o dostęp na panel admin z adresów 192.168.0.1 - 192.168.0.255. Poszukaj odpowiedzi o statusie 200.
* Darmowa wersja burpa nieco spowalnia proces tworzenia nowych requestów, dlatego warto odpalić burpIntrudera dwukrotnie, od zera z krokiem 1 i od 255 z krokiem -1.

</details>

link: https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-backend-system?fbclid=IwAR0d73LwAjne97NHERdkkcSTOougI_jBqTSB3jV0TI4cCyk3gTg4QRY5Qy4
