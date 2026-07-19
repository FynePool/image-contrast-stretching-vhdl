### Politecnico di Milano - Progetto Reti Logiche 2020-2021
## Test Generator

Batch di test generati con il [generatore Python](../../tools/generator-python) (`tools/generator-python/generator.py`). La cartella si chiamava originariamente `TestPassati + NuovoGeneratore (i da 3 e non da 2!!)`, a ricordo di una correzione applicata al testbench rispetto a una versione precedente (l'indice di lettura dei pixel di output doveva partire da `i = 2 + pix_num`, non da un offset errato).

## Contenuto delle sottocartelle

Ogni sottocartella contiene una coppia di file generati da `generator.py`:
- `ram_content.txt` — dati caricati in RAM, letti dal testbench VHDL
- `test_values.txt` — versione leggibile di ogni test (dimensioni immagine e pixel), per debug

| Cartella                         | Contenuto                                             |
|-----------------------------------|--------------------------------------------------------|
| `1test60x96`                      | 1 test, immagine 60x96                                  |
| `1test128x128`                    | 1 test, dimensione massima consentita (128x128)          |
| `5test128x128`                    | 5 test, dimensione 128x128                               |
| `40testRandom`                    | 40 test con dimensioni casuali                           |
| `2k tests, image limit 128`       | 2000 test con dimensioni casuali, limite 128              |
| `10k tests, image limit 16`       | 10000 test con dimensioni casuali, limite 16               |
| `TestRandom`                      | 100 test con dimensioni casuali, con l'output del testbench (`passati.txt` / `non_passati.txt`) |

I file `gen_testbench_reset.vhd` / `gen_testbench_no_reset.vhd` a livello di questa cartella (e dentro `TestRandom/`) sono copie del testbench di `tools/generator-python/`, con il percorso ai file di input/output già impostato per l'esecuzione originale su Vivado.

## How to import in Vivado

You can directly import the ```gen_testbench_reset.vhd``` (or ```gen_testbench_no_reset.vhd```) file as source in Vivado, then modify this file to match the folder containing the generated ram files. Instruction on how to modify it are included in the .vhd file itself.
