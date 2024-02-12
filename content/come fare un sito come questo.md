cosa useremo:
* [quartz](https://quartz.jzhao.xyz/): software che genera il sito web per noi
* account [github](https://github.com/): piattaforma per caricare online i file del sito web
* [git](https://git-scm.com/): per gestire i file, e caricarli online
* [obsidian](https://obsidian.md/): per scrivere i file che andranno su github

>[!warning]
>i comandi mostrati, funzionano su arch linux.

> [!note] in caso di problemi:
> segui la guida su: https://quartz.jzhao.xyz/
> oppure guarda questo video: https://www.youtube.com/watch?v=6s6DT1yN4dw&t=227s

## conoscenze pregresse
nulla di particolare, ma sarebbe comodo sapere:
* come scrivere testo in [markdown](https://www.markdownguide.org/) (nulla di complicato!)
* come funziona git (può essere abbastanza complicato)
## installare il software
se sei su arch linux:
```bash
sudo pacman -Syu
sudo pacman -S git # dovrebbe essere gia incluso su arch
sudo pacman -S npm nodejs
```
per installare `npm` e `nodejs`.  

> **npm**: software per gestire i pacchetti javascript, ci permette di installare quartz
> **nodejs**: esegue codice javascript

## per iniziare.
come riportato sulla wiki di quartz:
```bash
git clone https://github.com/jackyzha0/quartz.git
cd quartz
npm i
npx quartz create
```
* con `git clone ...`, viene creata una copia di **quartz** sul vostro computer. per "installare" quartz basta scaricare una cartella!
* `cd quartz` per entrare dentro la cartella
* `npm i` e `npm quartz create` per inizializzare il progetto

## come scrivo il mio sito web?
io uso [obsidian](https://obsidian.md/), e' un software per scrivere testo in formato [markdown](https://www.markdownguide.org/). il testo 
### esempio:

```markdown
# titolo 1
## titolo 2
questa e' una lista:
* 1
* 2
* 3

questa e' una lista numerata:
1. uno
2. due
3. tre

### titolo 3

```

---
# titolo 1
## titolo 2
questa e' una lista:
* 1
* 2
* 3

questa e' una lista numerata:
1. uno
2. due
3. tre

### titolo 3

---



