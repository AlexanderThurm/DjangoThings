> Deo ove sekcije je zasnovan na Geek Girls Carrots priručnicima (https://github.com/ggcarrots/django-carrots/).
> 
> Takođe, jedan deo je zasnovan na [django-marcador priručniku](http://django-marcador.keimlink.de/) pod Creative Commons Attribution-ShareAlike 4.0 International licencom. Sva prava za django-marcador priručnik zadržava Markus Zapke-Gründemann.

## Virtuelno okruženje

Pre nego što instaliramo Django, potrebno je instalirati prilično koristan alat koji je odgovoran za preglednost okruženja u kom se kodira. Ovaj korak se može preskočiti, ali to nije preporučljivo. Počinjanje sa najboljim mogućim podešavanjima će Vas poštedeti dosta muka u budućnosti!

Hajde da napravimo **virtuelno okruženje** (koje se takođe naziva još i *virtualenv*). Virtualenv će izolovati podešavanja za Python/Django za svaki projekat posebno. To znači da bilo koja izmena koju napravite na jednom sajtu neće imati uticaja na ostale sajtove koje trenutno pravite. Lepo, zar ne?

Sve što treba da uradite je da pronađete direktorijum u kom želite da kreirate `virtualenv`; na primer, vaš početni direktorijum. Na Windows-u, to bi trebalo da izgleda ovako `C:\Users\Name` (gde je `Name` ime vašeg naloga).

> **NAPOMENA:** Ukoliko koristite Windows, pobrinite se da ovaj direktorijum ne sadrži akcentovane ili neke specijalne karaktere. Ako Vaše korisničko ime sadrži akcentovane karaktere, upotrebite drugi direktorijum, npr. `C:\djangogirls`.

Za ovaj priručnik ćemo koristiti novi direktorijum `djangogirls`, iz Vašeg početnog direktorijuma:

{% filename %}command-line{% endfilename %}

    $ mkdir djangogirls
    $ cd djangogirls
    

Napravićemo virtualenv po imenu `myvenv`. Glavna komanda će biti u formatu:

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

<!--sec data-title="Virtual environment: Windows" data-id="virtualenv_installation_windows"
data-collapse=true ces-->

Kako biste kreirali novi `virtualenv`, potrebno je da otvorite komandnu liniju i da pokrenete `python -m venv myvenv`. To bi trebalo da izgleda ovako:

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls> python -m venv myvenv
    

Gde je `myvenv` ime Vašeg `virtualenv-a`. Možete da koristite bilo koje drugo ime, ali je potrebno da sadrži isključivo mala slova i da nema razmake, akcente ili neke specijalne karaktere. Takođe je dobra ideja da ime bude kratko, jer ćete ga često pisati.

<!--endsec-->

<!--sec data-title="Virtual environment: Linux and OS X" data-id="virtualenv_installation_linuxosx"
data-collapse=true ces-->

Možemo da kreiramo `virtualenv` i na Linux-u i na OS X, pokretanjem `python3 -m venv myvenv`. To bi trebalo da izgleda ovako:

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

`myvenv` je ime Vašeg `virtualenv-a`. Možete da koristite bilo koje drugo ime, ali je potrebno da sadrži isključivo mala slova i da nema razmake. Takođe je dobra ideja da ime bude kratko, jer ćete ga često pisati!

> **NAPOMENA:** Na nekim verzijama Debian/Ubuntu-a možete da dobijete sledeću grešku:
> 
> {% filename %}command-line{% endfilename %}
> 
>     The virtual environment was not created successfully because ensurepip is not available.  On Debian/Ubuntu systems, you need to install the python3-venv package using the following command.
>        apt install python3-venv
>     You may need to use sudo with that command.  After installing the python3-venv package, recreate your virtual environment.
>     
> 
> U tom slučaju, pratite instrukcije koje su prethodno navedene i instalirajte `python3-venv` paket: {% filename %}command-line{% endfilename %}
> 
>     $ sudo apt install python3-venv
>     
> 
> **NAPOMENA:** Na nekim verzijama Debian/Ubuntu-a, pokretanje virtuelnog okruženja vraća sledeću grešku:
> 
> {% filename %}command-line{% endfilename %}
> 
>     Error: Command '['/home/eddie/Slask/tmp/venv/bin/python3', '-Im', 'ensurepip', '--upgrade', '--default-pip']' returned non-zero exit status 1
>     
> 
> Kako biste to zaobišli, koristite komandu `virtualenv`.
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ sudo apt install python-virtualenv
>     $ virtualenv --python=python{{ book.py_version }} myvenv
>     
> 
> **NAPOMENA:** Ukoliko dobijete grešku
> 
> {% filename %}command-line{% endfilename %}
> 
>     E: Unable to locate package python3-venv
>     
> 
> Tada pokrenite:
> 
> {% filename %}command-line{% endfilename %}
> 
>     sudo apt install python{{ book.py_version }}-venv
>     

<!--endsec-->

## Rad sa virtualenv-om

Prethodne komande će da kreiraju direktorijum po imenu `myvenv` (ili možete da izaberete neko drugo ime) koje sadrži naše virtuelno okruženje (u suštini, pregršt direktorijuma i fajlova).

<!--sec data-title="Working with virtualenv: Windows" data-id="virtualenv_windows"
data-collapse=true ces-->

Pokrenite Vaše virtuelno okruženje komandom:

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls> myvenv\Scripts\activate
    

> **NAPOMENA:** na Windows 10 OS-u možete da dobijete grešku u Windows PowerShell-u koja kaže `izvršavanje skripti je onemogućeno na ovom sistemu`. U tom slučaju, otvorite još jedan Windows PowerShell pomoću opcije "Pokreni kao administrator". Zatim, pre pokretanja virtuelnog okruženja, ukucajte sledeću komandu:
> 
> {% filename %}command-line{% endfilename %}
> 
>     C:\WINDOWS\system32> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
>         Execution Policy Change
>         The execution policy helps protect you from scripts that you do not trust. Changing the execution policy might expose you to the security risks described in the about_Execution_Policies help topic at http://go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy? [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): A
>     

<!-- (This comment separates the two blockquote blocks, so that GitBook and Crowdin don't merge them into a single block.) -->

> **NOTE:** For users of the popular editor VS Code, which come with an integrated terminal based off windows PowerShell, if you wish to stick with the integrated terminal, you may run the following command to activate your virtual environment:
> 
>     $ . myvenv\Scripts\activate.ps1
>     
> 
> The advantage is that you don't have to switch between editor windows and command-line windows

<!--endsec-->

<!--sec data-title="Working with virtualenv: Linux and OS X" data-id="virtualenv_linuxosx"
data-collapse=true ces-->

Start your virtual environment by running:

{% filename %}command-line{% endfilename %}

    $ source myvenv/bin/activate
    

Remember to replace `myvenv` with your chosen `virtualenv` name!

> **NOTE:** sometimes `source` might not be available. In those cases try doing this instead:
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ . myvenv/bin/activate
>     

<!--endsec-->

You will know that you have `virtualenv` started when you see that the prompt in your console is prefixed with `(myvenv)`.

When working within a virtual environment, `python` will automatically refer to the correct version so you can use `python` instead of `python3`.

OK, we have all important dependencies in place. We can finally install Django!

## Installing Django {#django}

Now that you have your `virtualenv` started, you can install Django.

Before we do that, we should make sure we have the latest version of `pip`, the software that we use to install Django:

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ python -m pip install --upgrade pip
    

### Instaliranje paketa i neophodnih stavki

A requirements file keeps a list of dependencies to be installed using `pip install`:

First create a `requirements.txt` file inside of the `djangogirls/` folder, using the code editor that you installed earlier. You do this by opening a new file in the code editor and then saving it as `requirements.txt` in the `djangogirls/` folder. Your directory will look like this:

    djangogirls
    ├── myvenv
    │   └── ...
    └───requirements.txt
    

In your `djangogirls/requirements.txt` file you should add the following text:

{% filename %}djangogirls/requirements.txt{% endfilename %}

    Django~={{ book.django_version }}
    

Now, run `pip install -r requirements.txt` to install Django.

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ pip install -r requirements.txt
    Collecting Django~={{ book.django_version }} (from -r requirements.txt (line 1))
      Downloading Django-{{ book.django_version }}-py3-none-any.whl (7.1MB)
    Installing collected packages: Django
    Successfully installed Django-{{ book.django_version }}
    

<!--sec data-title="Installing Django: Windows" data-id="django_err_windows"
data-collapse=true ces-->

> If you get an error when calling pip on Windows platform, please check if your project pathname contains spaces, accents or special characters (for example, `C:\Users\User Name\djangogirls`). If it does, please consider using another place without spaces, accents or special characters (suggestion: `C:\djangogirls`). Create a new virtualenv in the new directory, then delete the old one and try the above command again. (Moving the virtualenv directory won't work since virtualenv uses absolute paths.)

<!--endsec-->

<!--sec data-title="Installing Django: Windows 8 and Windows 10" data-id="django_err_windows8and10"
data-collapse=true ces-->

> Your command line might freeze after when you try to install Django. If this happens, instead of the above command use:
> 
> {% filename %}command-line{% endfilename %}
> 
>     C:\Users\Name\djangogirls> python -m pip install -r requirements.txt
>     

<!--endsec-->

<!--sec data-title="Installing Django: Linux" data-id="django_err_linux"
data-collapse=true ces-->

> If you get an error when calling pip on Ubuntu 12.04 please run `python -m pip install -U --force-reinstall pip` to fix the pip installation in the virtualenv.

<!--endsec-->

That's it! You're now (finally) ready to create a Django application!