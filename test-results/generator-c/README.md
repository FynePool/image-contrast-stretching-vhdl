# test-results/generator-c

Batch di test eseguiti con il modulo finale usando dati generati dal [generatore in C](../../tools/generator-c) (`tools/generator-c/generatore`, testbench `multipleTests.vhd`). Ogni sottocartella è un batch indipendente e contiene, per convenzione del vecchio generatore (vedi il [README di tools/generator-c](../../tools/generator-c/README.txt)):

- `ramData1.txt` — dati caricati in RAM per l'esecuzione dei test del batch
- `ramResult1.txt` — soluzioni attese, usate dal testbench per il confronto
- `test.txt` (o `test1.txt`) — versione leggibile dei test generati
- `NotPassed.txt` — output del testbench: elenco dei pixel risultati errati (vuoto/assente se tutti i test sono passati)

## Batch presenti

| Cartella                       | Contenuto                                                        |
|---------------------------------|-------------------------------------------------------------------|
| `1Test-Size(0x0)`                | Caso limite: immagine 0x0 (nessun pixel). Include `0x0onWEwrites0.PNG`, screenshot che documenta il comportamento di `o_we`/`o_data` in questo caso limite |
| `1Test-Size(NULL)`               | Caso limite analogo, dimensioni nulle                              |
| `1Test-Size(128x128)`            | Caso limite: dimensione massima consentita dalla specifica (128x128) |
| `100RandomTests-Size(1-128)`     | 100 test con righe/colonne casuali nel range 1-128                 |
| `500RandomTests`                 | 500 test casuali                                                   |
| `2000RandomTests`                | 2000 test casuali                                                   |

Tutti i batch risultano passati (i file `NotPassed.txt` non riportano errori).
