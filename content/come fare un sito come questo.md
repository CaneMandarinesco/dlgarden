cosa useremo:
* [quartz](https://quartz.jzhao.xyz/): il software che genera il sito web per noi
* account [github](https://github.com/): piattaforma per caricare online i file del sito web
* [git](https://git-scm.com/): per gestire i file, e caricarli online
* [obsidian](https://obsidian.md/): per scrivere i file che andranno su github

>[!warning]
>i comandi mostrati, come `pacman`, funzionano su arch linux.

> [!note] in caso di problemi:
> segui la guida su: https://quartz.jzhao.xyz/
> oppure guarda questo video: https://www.youtube.com/watch?v=6s6DT1yN4dw&t=227s

## conoscenze pregresse
nulla di particolare, ma ti farebbe comodo sapere:
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

> **npm**: software per gestire i pacchetti javascript.
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
* `cd quartz` per entrare dentro la cartella con dentro il tuo sito web
* `npm i` e `npm quartz create` per inizializzare il progetto

## come scrivo il mio sito web?
per scrivere il sito web non serve sapere scrivere in *javascript*, *css*, ecc... basta scrivere usando il formato [markdown](https://www.markdownguide.org/)! per scrivere in markdown si puo' usare un editor di testo qualsiasi. **vscode** va benissimo, ma io preferisco usare [obsidian](https://obsidian.md/).  
obsidian, non e' solo un software per scrivere, infatti e' costruito in modo tale da comportarsi come un "secondo cervello".  
con obsidian puoi avere una *panoramica* di tutte le tue note e dei collegamenti tra queste grazie alla **graph view**:
![[Pasted image 20240214121422.png]]

## scrivere la pagina index
con il tuo editor preferito, apri la cartella `quartz/content`. qui e' dove risiedono le tue pagine web.  
all'interno dovrebbe gia' esserci un file: `index.md`. questo file e' la prima pagina che viene caricata quando si accede al sito, quindi questa pagina dovrebbe essere organizzata in modo tale da riassumere tutti i contenuti del tuo sito e contenere i link per raggiungere le pagine (fai riferimento alla mia pagina [[index]]).
puoi cominciare a sperimentare scrivendo su questo file, per aggiungere altre pagine basta aggiungere altri file `.md` nella cartella content. 

## caricare una preview del sito
una volta che hai scritto qualcosa sulla pagina index, puoi avviare una **preview** del tuo sito sul tuo computer con questo comando:
```bash
npx quartz build --serve
```
ora andando sul tuo browser, caricando l'indirizzo: http://localhost:8080/ potrai navigare sul tuo sito.

> [!note] attenzion!
> il tuo sito non e' ancora **pubblico**, infatti il link e' "visitabile" solo dal tuo computer!

## come rendere pubblico il sito web?
per prima cosa bisogna devi creare un **repository** su [github](https://github.com):
* cerca il tasto "crea nuovo repository"
* dagli un nome
* impostalo come *privato*
* clicca su "crea repository"

ora bisogna dire a *git* dove si trova su internet il tuo repository:
```bash
git remote set-url origin REMOTE-URL
```
dove `REMOTE-URL` va sostituito con **l'url** che porta alla pagina del tuo repository su github

ora bisogna dire a github che il tuo repository deve essere caricato come se fosse un sito web: