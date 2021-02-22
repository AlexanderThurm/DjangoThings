# Introduktion till HTML

Du kanske undrar vad en mall är?

En mall är en fil som vi kan återanvända för att presentera information med olika innehåll i ett konsekvent format – till exempel kan du använda en mall för att hjälpa dig att skriva ett brev. För även om varje brev kan innehålla olika meddelanden och adresseras till olika personer, kommer de att dela samma format.

En Django-malls format skrivs på ett språk som heter HTML (det är den HTML vi nämnde i det första kapitlet, **Hur Internet fungerar**).

## Vad är HTML?

HTML är kod som tolkas av din webbläsare – till exempel Chrome, Firefox eller Safari – för att visa en webbsida för användaren.

HTML står för "HyperText Markup Language". **HyperText** betyder att det är en typ av text som stöder hyperlänkar mellan sidor. **Markup** betyder att vi har tagit ett dokument och markerat det med kod för att berätta något (i det här fallet, en webbläsare) hur man tolkar sidan. HTML-kod är byggd med **taggar**, var och en som börjar med `<` och slutar med `>`. Dessa taggar representerar markup-**element**.

## Din första mall!

Att skapa en mall innebär att skapa en mallfil. Allt är en fil, eller hur? Du har förmodligen märkt detta redan.

Mallar sparas i katalogen `blog/templates/blog` . Så skapa först en katalog som heter `templates` i katalogen blog. Skapa därefter en annan katalog som heter `blog` i din mallkatalog:

    blog
    └───templates
        └───blog
    

(Du kanske undrar varför vi behöver två kataloger som båda heter `blog` – som du kommer att upptäcka senare är detta en användbar namnkonvention som gör livet lättare när saker och ting börjar bli mer komplicerade.)

Skapa nu filen `post_list.html` (lämna den tom för nu) i katalogen `blog/templates/blog` .

Se nu hur din webbplats ser ut: http://127.0.0.1:8000/

> Om du fortfarande får ett fel `TemplateDoesNotExist`, försök att starta om din server. Gå till kommandoraden, stoppa servern genom att trycka på Ctrl+C (Control- och C-tangenten tillsammans) och starta den igen genom att köra kommandot `python manage.py runserver`.

![Figur 11.1](images/step1.png)

No error anymore! Congratulations! :) However, your website isn't actually publishing anything except an empty page, because your template is empty too. We need to fix that.

Öppna den nya filen i kodeditorn, och lägg till följande:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<!DOCTYPE html>
<html>
<body>
    <p>Hi there!</p>
    <p>It works!</p>
</body>
</html>
```

Hur ser din webbplats ut nu? Besök den för att få veta: http://127.0.0.1:8000/

![Figur 11.2](images/step3.png)

It worked. Nice work there! :)

* The line `<!DOCTYPE html>` is not a HTML tag. It only declares the document type. Here, it informs the browser that document type is [HTML5](https://html.spec.whatwg.org/#the-doctype). This is always the beginning of any HTML5 file.
* The most basic tag, `<html>`, is always the beginning of html content and `</html>` is always the end. As you can see, the whole content of the website goes between the beginning tag `<html>` and closing tag `</html>`
* `<p>` is a tag for paragraph elements; `</p>` closes each paragraph

## Head och body

Varje HTML-sida är också uppdelad i två element: **head** och **body**.

* **head** är ett element som innehåller information om dokumentet som inte visas på skärmen.

* **body** är ett element som innehåller allt annat som visas som en del av webbsidan.

Vi använder `<head>` för att berätta för webbläsaren om konfigurationen av sidan, och `<body>` för att berätta vad som faktiskt finns på sidan.

Du kan till exempel lägga in en webbsidas titel-element i `<head>`, så här:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Ola's blog</title>
    </head>
    <body>
        <p>Hi there!</p>
        <p>It works!</p>
    </body>
</html>
```

Spara filen och ladda om sidan.

![Figur 11.3](images/step4.png)

Märkte du hur webbläsaren har förstått att "Ola's blog" är titeln på din sida? Den har tolkat `<title>Ola's blog</title>` och placerat texten i titelfältet i din webbläsare (den kommer också att användas för bokmärken och så vidare).

Förmodligen har du också märkt att varje öppningstagg matchas av en *stängningstagg*, med ett `/`, och att elementen är *nästlade* (dvs du kan inte stänga en viss tagg förrän alla som var inne i den också har stängts).

Det är som att lägga saker i lådor. Du har en stor låda, `<html></html>`; inuti den finns `<body></body>`, och den innehåller ännu mindre lådor: `<p></p>`.

Du måste följa dessa regler för *stängnings*-taggar, och för *nästlade* element – om du inte gör det kan webbläsaren kanske inte tolka dem korrekt och din sida kommer att visas felaktigt.

## Anpassa din mall

Du kan nu ha lite skoj och försöka anpassa din mall! Här är några användbara taggar:

* `<h1>En rubrik</h1>` för din viktigaste rubrik
* `<h2>En underrubrik</h2>` för en rubrik på nästa nivå
* `<h3>En under-underrubrik</h3>` …och så vidare, upp till `<h6>`
* `<p>Ett stycke text</p>`
* `<em>text</em>` betonar din text
* `<strong>text</strong>` betonar starkt din text
* `<br>` går till en annan rad (du kan inte sätta något inuti br och det finns ingen stängningstagg)
* `<a href="https://djangogirls.org">länk</a>` skapar en länk
* `<ul><li>första elementet</li><li>andra elementet</li></ul>` skapar en lista, precis som denna!
* `<div></div>` definierar ett avsnitt på sidan
* `<nav></nav>` defines a set of navigation links
* `<article></article>` specifies independent, self-contained content
* `<section></section>` defines a section in a document
* `<header></header>` specifies a header for a document or section
* `<main></main>` specifies the main content of a document
* `<aside></aside>` defines some content aside from the content it is placed in (like a sidebar)
* `<footer></footer>` defines a footer for a document or section
* `<time></time>` defines a specific time (or datetime)

Här är ett exempel på en komplett mall, kopiera och klistra in den i `blog/templates/blog/post_list.html`:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Django Girls blog</title>
    </head>
    <body>
        <header>
            <h1><a href="/">Django Girls Blog</a></h1>
        </header>

        <article>
            <time>published: 14.06.2014, 12:14</time>
            <h2><a href="">My first post</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</p>
        </article>

        <article>
            <time>published: 14.06.2014, 12:14</time>
            <h2><a href="">My second post</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut f.</p>
        </article>
    </body>
</html>
```

We've created one `header` section and two `article` section here.

* The `header` element contains the title of our blog – it's a heading and a link
* Another two `article` elements contain our blog posts with a published date in a `time` element, a `h2` element with a post title that is clickable and a `p` (paragraph) element for text of our blog post.

Det ger oss denna effekt:

![Figur 11.4](images/step6.png)

Yaaay! Men hittills visar vår mall bara exakt **samma information** hela tiden – medan vi tidigare pratade om mallar som tillåter oss att visa **olika** information i **samma format**.

Vad vi verkligen vill göra är att visa riktiga inlägg som lagts till i vår Django admin – och det är dit vi ska härnäst.

## En sak till: driftsätt!

Det skulle vara bra att se allt detta leva på Internet, eller hur? Låt oss göra ytterligare en driftsättning på PythonAnywhere:

### Commita och pusha din kod till GitHub

Allra först, låt oss se vilka filer som har ändrats sedan vi senast driftsatte (kör dessa kommandon lokalt, inte på PythonAnywhere):

{% filename %}command-line{% endfilename %}

    $ git status
    

Se till att du är i katalogen `djangogirls` och säg till `git` att inkludera alla ändringar i denna katalog:

{% filename %}command-line{% endfilename %}

    $ git add .
    

Innan vi laddar upp alla filer, låt oss kontrollera vad `git` kommer att ladda upp (alla filer som `git` kommer ladda upp ska visas i grönt):

{% filename %}command-line{% endfilename %}

    $ git status
    

Vi är nästan klara, nu är det dags att berätta för git att spara den här förändringen i dess historik. Vi kommer att ange ett "commit-meddelande" där vi beskriver vad vi har ändrat. Du kan skriva vad du vill i detta skede, men det är bra att skriva något beskrivande så att du i framtiden kan komma ihåg vad du har gjort.

{% filename %}command-line{% endfilename %}

    $ git commit -m "Changed the HTML for the site."
    

> **Note** Make sure you use double quotes around the commit message.

När vi har gjort det så laddar vi upp (pushar) våra ändringar till GitHub:

{% filename %}command-line{% endfilename %}

    $ git push
    

### Dra ner din nya kod till PythonAnywhere och ladda om din webbapp

* Öppna sidan [PythonAnywhere consoles page](https://www.pythonanywhere.com/consoles/) och gå till din **Bash-konsol** (eller starta en ny). Kör sedan:

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ cd ~/<your-pythonanywhere-domain>.pythonanywhere.com
    $ git pull
    [...]
    

Du måste ersätta `<your-pythonanywhere-domain>` med ditt faktiska subdomännamn utan vinkelparenteser. Ditt subdomännamn är normalt sett ditt användarnamn på PythonAnywhere men i vissa fall kan det vara lite annorlunda (t.ex. om ditt användarnamn innehåller stora bokstäver). Så om detta kommando inte fungerar, använd kommandot `ls` (listar filer) för att hitta din faktiska subdomän/mappnamn och kör `cd` dit.

Se nu hur din kod laddas ner. Om du vill kontrollera att den har anlänt, kan du hoppa över till sidan **"Files"** och visa din kod på PythonAnywhere (du kan nå andra PythonAnywhere-sidor från menyknappen på konsolsidan).

* Slutligen, hoppa över till sidan ["Web"](https://www.pythonanywhere.com/web_app_setup/) och klicka på **Reload** på din webbapp.

Din uppdatering bör vara live! Gå vidare och uppdatera din webbsida webbläsaren. Ändringarna bör vara synliga. :)