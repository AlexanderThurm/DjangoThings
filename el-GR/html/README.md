# Εισαγωγή στην HTML

Ίσως αναρρωτιέστε, τι είναι ένα template;

Ένα template είναι ένα αρχείο που μπορούμε να επαναχρησιμοποιούμε για να παρουσιάζουμε διαφορετικές πληροφορίες μέσα από μια συνεπή μορφή. Για παράδειγμα, θα μπορούσατε να χρησιμοποιήσετε ένα πρότυπο (template) για να σας βοηθήσει να γράψετε μια επιστολή, γιατί αν και κάθε επιστολή μπορεί να περιέχει διαφορετικό μήνυμα και να απευθύνεται σε ένα διαφορετικό πρόσωπο, μερικά σημεία θα μοιραστούν την ίδια μορφή.

Η μορφή ενός Django template περιγράφεται με μια γλώσσα που ονομάζεται HTML (που είναι η HTML που αναφέραμε στο πρώτο κεφάλαιο, **Πώς λειτουργεί το Internet**).

## Τι είναι η HTML;

Η HTML είναι ένας κώδικας που ερμηνεύεται από τον web browser σας – όπως ο Chrome, Firefox ή Safari - για να εμφανιστεί μια ιστοσελίδα στον χρήστη.

HTML σημαίνει "HyperText Markup Language". Η λέξη **HyperText** σημαίνει ότι είναι ένας τύπος κειμένου που υποστηρίζει υπερ-συνδέσεις μεταξύ των σελιδών. **Markup** σημαίνει ότι έχουμε λάβει ένα έγγραφο και το έχουμε επισημάνει με κώδικα ούτως ώστε να πει κάτι (στην προκειμένη περίπτωση, ένας browser) πώς να ερμηνεύσει τη σελίδα. Ο HTML κώδικας είναι χτισμένος με **tags**, όπου καθένα αρχίζει με `<` και τελειώνει με `>`. Αυτά τα tags αντιπροσωπεύουν τα markup **elements**.

## Το πρώτο σας template!

H δημιουργία ενός template σημαίνει τη δημιουργία ενός αρχείου template. Τα πάντα είναι ένα αρχείο, σωστά; Πιθανώς να το έχετε παρατηρήσει αυτό.

Τα templates αποθηκεύονται στο φάκελο `blog/templates/blog`. Άρα, πρώτα δημιουργήστε έναν φάκελο με το όνομα `templates` μέσα στον φάκελο blog. Στη συνέχεια, δημιουργήστε έναν άλλο φάκελο που ονομάζεται `blog` μέσα στον φάκελο templates:

    blog
    └───templates
        └───blog
    

(Ίσως να αναρωτηθείτε γιατί χρειαζόμαστε δύο φακέλους που και οι δύο ονομάζονται `blog`. Όπως θα ανακαλύψετε αργότερα, αυτό είναι μια τεχνική ονομασίας που κάνει τη ζωή ευκολότερη όταν τα πράγματα αρχίζουν να περιπλέκονται.)

Και τώρα δημιουργήστε ένα αρχείο `post_list.html` (απλά αφήστε το κενό για τώρα) μέσα στον φάκελο `blog/templates/blog`.

Δείτε πώς εμφανίζεται η ιστοσελίδα σας στο: http://127.0.0.1:8000 /

> Αν παρουσιάζεται ακόμα το σφάλμα `TemplateDoesNotExist`, δοκιμάστε να επανεκκινήσετε τον server σας. Προσπαθήστε να τον σταματήσετε (πιέζοντας Ctrl + C) και επανεκκινήστε τον τρέχοντας την εντολή `python manage.py runserver`.

![Σχήμα 11.1](images/step1.png)

No error anymore! Congratulations! :) However, your website isn't actually publishing anything except an empty page, because your template is empty too. We need to fix that.

Ανοίξτε το νέο αρχείο και προσθέστε τα εξής:

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

Οπότε πως φαίνεται τώρα η ιστοσελίδα μας; Επισκεφθείτε το για να μάθετε: http://127.0.0.1:8000/

![Σχήμα 11.2](images/step3.png)

It worked. Nice work there! :)

* The line `<!DOCTYPE html>` is not a HTML tag. It only declares the document type. Here, it informs the browser that document type is [HTML5](https://html.spec.whatwg.org/#the-doctype). This is always the beginning of any HTML5 file.
* The most basic tag, `<html>`, is always the beginning of html content and `</html>` is always the end. As you can see, the whole content of the website goes between the beginning tag `<html>` and closing tag `</html>`
* `<p>` is a tag for paragraph elements; `</p>` closes each paragraph

## Head και body

Κάθε σελίδα HTML χωρίζεται σε δύο στοιχεία: το **head** και το **body**.

* To **head** είναι ένα στοιχείο (element) που περιέχει πληροφορίες σχετικά με το έγγραφο αλλά αυτές οι πληροφορίες δεν εμφανίζονται στην οθόνη.

* Το **body** είναι ένα στοιχείο που περιέχει όλα τα υπόλοιπα που εμφανίζονται ως μέρος της ιστοσελίδας.

Χρησιμοποιούμε το tag `<head>`για να πούμε στον browser σχετικά με τη διαμόρφωση της σελίδας και το tag `<body>` για να πούμε για το περιεχόμενο της.

Για παράδειγμα, μπορείτε να προσθέσετε τίτλο στην ιστοσελίδα σας μέσα από το tag `<head>`, όπως παρακάτω:

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

Αποθηκεύστε το αρχείο και ανανέωστε την σελίδα σας.

![Σχήμα 11.3](images/step4.png)

Παρατηρήσατε πως ο browser κατάλαβε το "Ola's blog" ως τίτλο για την σελίδα σας; Ερμήνευσε το κείμενο `<title>Ola's blog</title>` και το τοποθέτησε στην μπάρα τίτλων του browser σας (το ίδιο κείμενο θα λειτουργήσει και ως όνομα σελιδοδείκτη κλπ).

Πιθανώς να έχετε παρατηρήσει ότι κάθε tag αντιστοιχίζεται με ένα *tag κλεισίματος*, με μια κάθετο `/` και ότι τα στοιχεία είναι *ένθετα* (δηλαδή δεν μπορείτε να κλείσετε μια συγκεκριμένη ετικέτα μέχρι να έχουν κλείσει όλα αυτά που ήταν μέσα σε αυτό).

Είναι σαν να βάζουμε πράγματα μέσα σε κουτιά. Έχετε ένα μεγάλο κουτί, `<html></html>`. Στο εσωτερικό του υπάρχει το `<body></body>` το οποίο με τη σειρά του περιέχει ακόμα μικρότερα κουτιά: `<p></p>`.

Θα πρέπει να ακολουθείτε αυτούς τους κανόνες *κλεισίματος ετικέτας* και *"φωλιάσματος"* των elements. Αν δεν το κάνετε, ο browser ενδέχεται να μην μπορεί να τα ερμηνεύσει ορθά και η σελίδα να μην εμφανίζεται σωστά.

## Παραμετροποιώντας το template

Μπορείτε, τώρα, να διασκεδάσετε λιγάκι και να τροποιήσετε το template σας! Παρακάτω παρουσιάζονται μερικά χρήσιμα tags γι'αυτό:

* `<h1>A heading</h1>` για επικεφαλίδες
* `<h2>A sub-heading</h2>` για επικεφαλίδες χαμηλότερου επιπέδου
* `<h3>A sub-sub-heading</h3>` …κοκ μέχρι την `<h6>`
* `<p>Μια παράγραφος κειμένου</p>`
* `<em>text</em>` δίνει έμφαση στο κείμενο σας
* `<strong>text</strong>` κάνει τα γράμματα πιο έντονα
* `<br>` αλλάζει γραμμή (δεν μπορείτε να βάλετε τίποτα ανάμεσα και δεν υπάρχει αντίστοιχο tag που να το κλείνει)
* `<a href="https://djangogirls.org">link</a>` δημιουργεί έναν σύνδεσμο
* `<ul><li>first item</li><li>second item</li></ul>` δημιουργεί μια λίστα, όπως αυτή εδώ που διαβάζετε τώρα!
* `<div></div>` ορίζει ένα τμήμα στη σελίδα
* `<nav></nav>` defines a set of navigation links
* `<article></article>` specifies independent, self-contained content
* `<section></section>` defines a section in a document
* `<header></header>` specifies a header for a document or section
* `<main></main>` specifies the main content of a document
* `<aside></aside>` defines some content aside from the content it is placed in (like a sidebar)
* `<footer></footer>` defines a footer for a document or section
* `<time></time>` defines a specific time (or datetime)

Παρακάτω φαίνεται ένα πλήρες παράδειγμα ενός template. Αντιγράψτε-επικολλήστε το μέσα στο αρχείο `blog/templates/blog/post_list.html`:

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
* The two `article` elements contain our blog posts with a published date in a `time` element, a `h2` element with a post title that is clickable and a `p` (paragraph) element for text of our blog post.

Δίνει αυτή την αίσθηση:

![Σχήμα 11.4](images/step6.png)

Ναιιι! Αλλά μέχρι στιγμής, το template μας εμφανίζει **τις ίδιες πληροφορίες** – ενώ προηγουμένως μιλούσαμε για templates που μας επέτρεπαν να εμφανίσουμε **διαφορετικές/δυναμικές** πληροφορίες με την **ίδια μορφή**.

Αυτό που θέλουμε να κάνουμε είναι να εμφανίσουμε πραγματικά posts τα οποία θα τα προσθέτουμε μέσω του Django admin. Και αυτό ακριβώς θα κάνουμε μετά.

## Ένα πράγμα ακόμα: ώρα να το ανεβάσετε!

Θα ήταν καλό να το δούμε όλο αυτό στο internet, σωστά; Ας κάνουμε άλλο ένα deploy στο PythonAnywhere:

### Κάντε commit και έπειτα push τον κώδικα σας στο GitHub

Πρώτ'απ'όλα ας δούμε ποια αρχεία έχουν αλλάξει από την τελευταία φορά που κάναμε deploy (τρέξτε αυτές τις εντολές τοπικά, όχι στο PythonAnywhere):

{% filename %}command-line{% endfilename %}

    $ git status
    

Σιγουρευτείτε ότι βρίσκεστε μέσα στο φάκελο `djangogirls` και ας πούμε στο `git` να συμπεριλάβει όλες τις αλλαγές μέσα σε αυτό το φάκελο:

{% filename %}command-line{% endfilename %}

    $ git add .
    

Πριν ανεβάσουμε όλα τα αρχεία, ας δούμε τι επρόκειτο να ανεβάσει το `git` (όλα τα αρχεία που επρόκειτο να ανεβούν από το `git` θα εμφανίζονται με πράσινο χρώμα):

{% filename %}command-line{% endfilename %}

    $ git status
    

Σχεδόν φτάσαμε. Τώρα είναι η ώρα να του πούμε να αποθηκεύσει αυτή την αλλαγή στο ιστορικό του. Θα του δώσουμε ένα "commit message" όπου θα περιγράψουμε τι άλλαξε. Μπορείτε να γράψετε ότι θέλετε σε αυτό το σημείο αλλά είναι χρήσιμο να γράψετε κάτι περιγραφικό ούτως ώστε να το θυμάστε στο μέλλον.

{% filename %}command-line{% endfilename %}

    $ git commit -m "Changed the HTML for the site."
    

> **Note** Make sure you use double quotes around the commit message.

Μόλις τελειώσουμε με αυτό, θα ανεβάσουμε (push) τις αλλαγές μας στο GitHub:

{% filename %}command-line{% endfilename %}

    $ git push
    

### Κάντε pull τον νέο σας κώδικα στο PythonAnywhere και ανανεώστε την εφαρμογή

* Έπειτα συνδεθείτε στο [PythonAnywhere](https://www.pythonanywhere.com/consoles/), μεταβείτε στο **Bash console** (ή ανοίξτε ένα νέο) και τρέξτε:

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ cd ~/<your-pythonanywhere-domain>.pythonanywhere.com
    $ git pull
    [...]
    

You'll need to substitute `<your-pythonanywhere-domain>` with your actual PythonAnywhere subdomain name, without the angle-brackets. Your subdomain name is normally your PythonAnywhere user name, but in some cases it might be a bit different (such as if your user name contains capital letters). So if this command doesn't work, use the `ls` (list files) command to find your actual subdomain/folder name, and then `cd` to there.

Now watch your code get downloaded. Αν θέλετε να δείτε ότι ολοκληρώθηκε, μεταβείτε στη σελίδα **"Files" page** και δείτε τον κώδικα σας στο PythonAnywhere (μπορείτε να ανοίξετε και άλλες σελίδες του PythonAnywhere από το κουμπί του μενού στην σελίδα της κονσόλας).

* Τέλος, πηγαίνετε στο ["Web" page](https://www.pythonanywhere.com/web_app_setup/) και κλικάρετε **Reload** στην εφαρμογή σας.

Οι αλλαγές θα πρέπει να είναι ορατές τώρα! Πηγαίνετε και ανανεώστε τη σελίδα στον browser σας. :)