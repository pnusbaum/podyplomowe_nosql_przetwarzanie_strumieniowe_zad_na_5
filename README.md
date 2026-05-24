# Zadanie zaliczeniowe na ocenę 5 — Kafka + PgVector + Neo4j
## Cel.
Zaprojektowanie i implementacja prostego systemu przetwarzania zdarzeń bankowych w
architekturze strumieniowej

# Realizacja

## Infrastruktura

Nietrywialnym dla mnie zadaniem było odpowiednie przygotowanie dockera by maszyna zawierała wszystkie wymagane komponenty
Dlatego też dodałem plik konfiguracyjny do projektu na githubie bym mógł ew w przyszłości z tego skorzystać
Wrzucilem to do folderu
```
infrastructure
```
Zwracam uwagę na inne porty niż domyślne z labów bo miałem sporo działąjących kontenerów i nie chcialem konfliktów
vscode uruchamiamy na adresie
```
http://localhost:8090/?folder=/home/coder
```

## Uwagi do realizacji

### 1. Transakcje

Transakcje wrzuciłem do pliku transactions.json

### 2. Cypher i embeddingi 

Nie jestem pewien czy treść zadania mówi o znalezieniu przelewów zawierających kontekst jedzenia I zwrotu środków, czy też mają być to osobne zapytania

Zrobiłem więc każdą z wersji

W przypadku wersji z łączeniem obu warunków, miałem trochę problemów by za pomocą cypher wyselekcjonować odpowiednie transakcje
Musiałem troche kombinować z embeddingiem ;) stąd ciekawe twory typu:
```
vec_refund = embed(["zwrot środków oddanie pieniędzy zwrot kosztów"])[0].tolist()
vec_food = embed(["jedzenie obiad pizza zakupy spożywcze"])[0].tolist()
```

### 3. SQL

Co do zapytania SQL to zmieniłem tylko warunek na timestamp żeby zwracał jakieś wyniki. Bo minus 3 dni zwracał pustość.


### 4. Odpowiedzi na wszystkie pytania z zadania

są wewnątrz notebooków consumerA i consumerB

