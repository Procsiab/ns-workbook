# ns-workbook

[![Build Status](https://ci.procsiab.cf/api/badges/Procsiab/ns-workbook/status.svg)](https://ci.procsiab.cf/Procsiab/ns-workbook)
[![Website](https://img.shields.io/website/https/book.procsiab.cf?down_message=offline&up_message=online)](https://book.procsiab.cf/)
[![Static](https://img.shields.io/badge/licenza-GFDLv1.3-yellowgreen.svg)](https://github.com/Procsiab/psi-2019/blob/master/LICENSE)

Eserciziario per il corso di Sicurezza delle Reti del prof. Bregni (Politecnico di Milano), realizzato a partire daalla raccolta di testi delle prove di esame, dal 2013 al 2019.

## Organizzazione del progetto

- `main.tex`: file principale, contenente preambolo, pagina del titolo e inclusione dei file per i capitoli;
- `chap*.tex`: file relativi ai capitoli, contengono unicamente il contenuto di ciascun capitolo;
- `title.tex`: file contenente lo stile della pagina iniziale, con titolo di copertina e licenza.

## Ottenere il PDF

Il PDF è generato da un sistema di continuous delivery, per avere sempre una versione compilata e aggiornata a partire dal sorgente.

Il sistema di integrazione pubblica PDF compilati a questo [indirizzo](https://book.procsiab.cf), dove saranno presenti anche i documenti compilati dalle altre repository pubbliche.

Ho scelto *Drone* per l'integrazione perché facile da mettere in funzione tramite container Docker; l'immagine che viene usata come base invece è un'installazione personalizzata di TexLive su ARMv7 (trovate qui il [Dockerfile](https://github.com/Procsiab/texlive-rpi-it)).

### Chi fa da sè...

Potete usare `make all` per ottenere il file PDF nella cartella omonima. I requisiti per compilare sono i seguenti:
- una installazione *texlive* 2019;
- il pacchetto *make*;
- il compilatore *latexmk*.

### Branch **devel**

Nel branch `devel` si trova il lavoro in corso degli appunti, mentre tutti i capitoli ultimati saranno accessibili dal branch `master`.

Il branch `devel` ospiterà in ogni caso anche tutto il codice del branch `master`, ma il file *src/main.tex* è impostato per compilare solamente il capitolo in corso.
