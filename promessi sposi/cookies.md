# RELASE 4.5.0
### In questa relase abbiamo introdotto i cookies, per fornire all'utente una migliore esperienza di ascolto.
### Crediamo che maggiore sia la comodità d'utilizzo del nostro servizio, più contento sarà l'utente finare che lo utilizzarà.

##  PER QURSTO OGGI INTRODUCIAMO I COOKIES, una tecnologia che permetterà ai nostri utenti di migliorare la loro esperienza di ascolto e di studio.
### in questo file spiegheremo come funzionano e come gli utilizziamo.
## <br><br><br>
# tutto parte dal lettore multimediale esterno.
### Tutto parte dal lettore multimediale esterno, che puoi utilizzare cliccando sul pulsante a lato di ogni file audio. <br> esso ti permette di riprodurre il file in una finestra (su desktop) o in una scheda (su mobile), separata. In questo modo puoi concentrarti meglio ed ottenere un'ascolto migliore. <br> Nel file .html che contiene il lettore c'è uno script [nelle righe da 35 a 37 di solito] che genera un cookie che viene memorizzato nel tuo browser.
```html
<script>
    Cookies.set('puntata', 'prima');
</script>
```
### poi, una volta ritornato alla home page del sito, un'altro script controllerà se c'è uno di questi cookie memorizzato nel browser e in caso affermativo, farà scorrere la pagina fino all'indice indicato dal cookie.
```html
<script>
    var puntata = Cookies.get('puntata');
    location.href = '#' + puntata;
    Cookies.remove('puntata');
</script>
```
### Come puoi notare, lo script controlla se nel browser è memorizzato un coockie di nome puntata, lo legge e ne assegna il valore alla variabile puntata
``` javascript
    var puntata = Cookies.get('puntata');
```
### poi effettua il reindirizzamento all'indice indicato dal cookie, infatti esso contiene un solo paramentro con all'interno scritto il numero della puntata ['prima', 'seconda', 'terza'... e così via] e lo script, concatenando il parametro ad un asterisco, reindirizza l'utente.

```javascript
location.href = '#' + puntata;
```
```
subdomain.domain.org/page#indice
```
### infine, per non causare errori con futuri cookies, lo script elimina il cookie.
```javascript
Cookies.remove('puntata');
```