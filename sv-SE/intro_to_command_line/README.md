# Introduktion till kommandotolken

> För läsare hemma: detta kapitel omfattas av videon [Your new friend: Command Line](https://www.youtube.com/watch?v=jvZLWhkzX-8).

Visst är det spännande!?! Inom bara några minuter kommer du skriva din första rad kod! :)

**Låt oss introducera dig till din första nya vän: kommandotolken!**

De följande stegen kommer att visa dig hur du använder det svarta fönstret som alla hackers använder. Det kan se lite läskigt ut i början, men egentligen är det bara ett fönster som väntar på instruktioner från dig.

> **Obs** Genom hela denna bok används termerna 'katalog' och 'mapp' synonymt.

## Vad är kommandotolken?

Fönstret, som oftast kallas **kommandotolken** eller **terminalen**, är ett textbaserat program för att visa, hantera och ändra filer på din dator. Ungefär som Windows Utforskaren eller Finder på Mac, men utan det grafiska gränssnittet. Andra namn på kommandotolken är: *cmd*, *CLI*, *prompt*, *konsol* eller *terminal*.

## Öppna kommandotolken

För att starta några experiment så behöver vi öppna kommandotolken.

{% include "/intro_to_command_line/open_instructions.md" %}

## Prompt

Du borde nu se ett vitt eller svart fönster som väntar på dina kommandon.

<!--sec data-title="Prompt: OS X and Linux" data-id="OSX_Linux_prompt" data-collapse=true ces-->

Om du är på Mac eller Linux, så ser du nog en `$`, såhär:

{% filename %}command-line{% endfilename %}

    $
    

<!--endsec-->

<!--sec data-title="Prompt: Windows" data-id="windows_prompt2" data-collapse=true ces-->

På Windows, så ser du nog en `>`, såhär:

{% filename %}command-line{% endfilename %}

    >
    

Kolla på Linux-sektionen precis ovan nu -- du kommer att se mer som det när du kommer till PythonAnywhere senare i handledningen.

<!--endsec-->

Varje kommando kommer att infogas av ett `$` eller `>` och ett mellanrum, men du ska inte skriva det. Din dator kommer att göra det åt dig. :)

> En liten notis: i ditt fall kan det vara något som `C:\Users\ola>` eller `Olas-MacBook-Air:~ ola$` och det är 100% OK.

Delen fram till och med `$` eller `>` kallas *kommandoradsprompten* eller kort och gott *prompten*. Den uppmanar dig att mata in något där.

I handledningen, när vi vill att du ska skriva in ett kommando, kommer vi att inkludera `$` eller `>`, och ibland ännu mer till vänster. Ignorera den vänstra delen och skriv bara in kommandot, som börjar efter prompten.

## Ditt första kommando (WOHO!)

Börja med att skriva detta kommando:

<!--sec data-title="Your first command: OS X and Linux" data-id="OSX_Linux_whoami" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ whoami
    

<!--endsec-->

<!--sec data-title="Your first command: Windows" data-id="windows_whoami" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > whoami
    

<!--endsec-->

Och tryck sedan `Enter`. Detta blir resultatet:

{% filename %}command-line{% endfilename %}

    $ whoami
    olasitarska
    

Som ni kan se har datorn precis skrivit ut ditt användarnamn. Snyggt, va? :)

> Försök att skriva varje kommando för hand, utan att kopiera och klistra in. På så sätt kommer du komma ihåg bättre!

## Grunderna

Varje operativsystem har lite olika kommandon för terminalen, så följ instruktionerna för ditt operativsystem. Nu kör vi!

### Aktuell katalog

Visst hade det varit bra att veta var vi är? Skriv in detta kommando och tryck `enter`:

<!--sec data-title="Current directory: OS X and Linux" data-id="OSX_Linux_pwd" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ pwd
    /Users/olasitarska
    

> Notis: 'pwd' står för 'print working directory', alltså 'skriv ut nuvarande mapp'.

<!--endsec-->

<!--sec data-title="Current directory: Windows" data-id="windows_cd" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd
    C:\Users\olasitarska
    

> Note: 'cd' stands for 'change directory'. With PowerShell you can use pwd just like on Linux or Mac OS X.

<!--endsec-->

Du ser säkert något liknande på din dator. När du öppnar terminalen brukar du starta i användarens hemmamapp.

* * *

### Lär dig mer om ett kommando

Många kommandon som du kan skriva i kommandotolken har inbyggd hjälp som du kan visa och läsa! Till exempel, för att lära sig mer om kommandot som visar vilken mapp du är i:

<!--sec data-title="Command help: OS X and Linux" data-id="OSX_Linux_man" data-collapse=true ces-->

OS X och Linux har ett `man` kommando, vilket ger dig hjälp med kommandon. Testa `man pwd` och se vad den säger, eller lägg `man` före andra kommandon för att se hjälp om dem. Utmatningen av `man` har normalt sidor. Använd mellanslag för att gå till nästa sida, och `q` för att sluta visa hjälpsidan.

<!--endsec-->

<!--sec data-title="Command Help: Windows" data-id="windows_help" data-collapse=true ces-->

Om du lägger till `/?` suffix till flesta kommandon kommer att visa hjälpsidan. Du kan behöva skrolla upp i kommandotolken för att se allt. Testa `cd /?`.

<!--endsec-->

### Lista filer och mappar

Så vad finns här? Det hade varit kul att se. Vi testar:

<!--sec data-title="List files and directories: OS X and Linux" data-id="OSX_Linux_ls" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ ls
    Applications
    Desktop
    Downloads
    Music
    ...
    

<!--endsec-->

<!--sec data-title="List files and directories: Windows" data-id="windows_dir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > dir
     Directory of C:\Users\olasitarska
    05/08/2020 07:28 PM <DIR>      Applications
    05/08/2020 07:28 PM <DIR>      Desktop
    05/08/2020 07:28 PM <DIR>      Downloads
    05/08/2020 07:28 PM <DIR>      Music
    ...
    

> Note: In PowerShell you can also use 'ls' like on Linux and Mac OS X. <!--endsec-->

* * *

### Ändra aktuell mapp

Låt oss gå till Skrivbordets mapp:

<!--sec data-title="Change current directory: OS X" data-id="OSX_move_to" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ cd Desktop
    

<!--endsec-->

<!--sec data-title="Change current directory: Linux" data-id="Linux_move_to" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ cd Desktop
    

Notera att mapp-namnet "Desktop" kan vara översatt till språket på ditt Linux-konto. Om det är så, så behöver du ändra `Desktop` till det översatta ordet; till exempel, `Schreibtisch` på Tyska.

<!--endsec-->

<!--sec data-title="Change current directory: Windows" data-id="windows_move_to" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd Desktop
    

<!--endsec-->

Kolla om det verkligen är ändrat:

<!--sec data-title="Check if changed: OS X and Linux" data-id="OSX_Linux_pwd2" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ pwd
    /Users/olasitarska/Desktop
    

<!--endsec-->

<!--sec data-title="Check if changed: Windows" data-id="windows_cd2" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd
    C:\Users\olasitarska\Desktop
    

<!--endsec-->

Här är det!

> Tips: Om du skriver `cd D` och sen klickar på `tab` på ditt tangentbord, så kommer kommandotolken att automatiskt skriva in resten av namnet för att navigera snabbare. Om det finns fler än en mapp som startar med "D", klicka på `tab` tangenten två gånger för att få en lista med alternativ.

* * *

### Skapa mapp

Vad sägs om att skapa en test-mapp på ditt skrivbord? Du kan göra det så här:

<!--sec data-title="Create directory: OS X and Linux" data-id="OSX_Linux_mkdir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ mkdir övning
    

<!--endsec-->

<!--sec data-title="Create directory: Windows" data-id="windows_mkdir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > mkdir övning
    

<!--endsec-->

Det här lilla kommandot kommer att skapa en mapp med namnet `övning` på ditt skrivbord. Du kan kolla om det är där genom att kolla på ditt skrivbord eller genom att göra `ls` eller `dir` kommandot! Prova det. :)

> Tips: Om du inte vill skriva samma kommando om och om igen, försök trycka på `uppåtpilen` och `nedåtpilen` på ditt tangentbord för att bläddra bland kommandon som du nyligen använt.

* * *

### Övning!

En liten utmatning för dig: i din nyligen skapade `övning` mapp, skapa en mapp som heter `test`. (Använd `cd` och `mkdir` kommandona.)

#### Lösning:

<!--sec data-title="Exercise solution: OS X and Linux" data-id="OSX_Linux_test_dir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ cd övning
    $ mkdir test
    $ ls
    test
    

<!--endsec-->

<!--sec data-title="Exercise solution: Windows" data-id="windows_test_dir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd practice
    > mkdir test
    > dir
    05/08/2020 07:28 PM <DIR>      test
    

<!--endsec-->

Grattis!

* * *

### Rensa upp

Vi vill inte lämna en röra, så låt oss ta bort allt som vi gjort tills nu.

Först, måste vi gå tillbaka till Skrivbordet:

<!--sec data-title="Clean up: OS X and Linux" data-id="OSX_Linux_back" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ cd ..
    

<!--endsec-->

<!--sec data-title="Clean up: Windows" data-id="windows_back" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd ..
    

<!--endsec-->

Om man använder `..` med `cd` kommandot så kommer det att ändra din nuvarande mapp till förälder mappen (det är, mappen som innehåller din nuvarande mapp).

Kolla var du är:

<!--sec data-title="Check location: OS X and Linux" data-id="OSX_Linux_pwd3" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ pwd
    /Users/olasitarska/Desktop
    

<!--endsec-->

<!--sec data-title="Check location: Windows" data-id="windows_cd3" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd
    C:\Users\olasitarska\Desktop
    

<!--endsec-->

Nu är det dags att radera `övning` mappen:

> **Varning**: Borttagning av filer med `del`, `rmdir` eller `rm` är oåterkalleligt, alltså är *de raderade filerna borta för alltid*! Så var väldigt försiktig med det här kommandot.

<!--sec data-title="Delete directory: Windows Powershell, OS X and Linux" data-id="OSX_Linux_rm" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ rm -r övning
    

<!--endsec-->

<!--sec data-title="Delete directory: Windows Command Prompt" data-id="windows_rmdir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > rmdir /S övning
    övning, Are you sure <Y/N>? Y
    

<!--endsec-->

Klart! För att vara säker på att den är raderad, låt oss kolla:

<!--sec data-title="Check deletion: OS X and Linux" data-id="OSX_Linux_ls2" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ ls
    

<!--endsec-->

<!--sec data-title="Check deletion: Windows" data-id="windows_dir2" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > dir
    

<!--endsec-->

### Avsluta

Nu är det klart för nu! Du kan nu stänga kommandotolken. Låt oss göra det på hacker sättet, okej? :)

<!--sec data-title="Exit: OS X and Linux" data-id="OSX_Linux_exit" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ exit
    

<!--endsec-->

<!--sec data-title="Exit: Windows" data-id="windows_exit" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > exit
    

<!--endsec-->

Coolt, va? :)

## Sammanfattning

Här är en sammanfattning av några viktiga kommandon:

| Kommando (Windows) | Kommando (Mac OS / Linux) | Beskrivning              | Exempel                                               |
| ------------------ | ------------------------- | ------------------------ | ----------------------------------------------------- |
| exit               | exit                      | stäng fönstret           | **exit**                                              |
| cd                 | cd                        | ändra katalog            | **cd test**                                           |
| cd                 | pwd                       | visa nuvarande katalog   | **cd** (Windows) eller **pwd** (Mac OS / Linux)       |
| dir                | ls                        | lista kataloger/filer    | **dir**                                               |
| copy               | cp                        | kopiera fil              | **copy c:\test\test.txt c:\windows\test.txt**     |
| move               | mv                        | flytta fil               | **move c:\test\test.txt c:\windows\test.txt**     |
| mkdir              | mkdir                     | skapa en ny katalog      | **mkdir testkatalog**                                 |
| rmdir (eller del)  | rm                        | ta bort en fil           | **del c:\test\test.txt**                            |
| rmdir /S           | rm -r                     | ta bort en mapp          | **rm -r testkatalog**                                 |
| [CMD] /?           | man [CMD]                 | få hjälp om ett kommando | **cd /?** (Windows) eller **man cd** (Mac OS / Linux) |

Dessa är få av alla andra kommandon som du kan köra i kommandotolken, men du kommer inte att använda fler än de idag.

Om du är nyfiken så innehåller [ss64.com](http://ss64.com) en komplett lista med kommandon för alla operativsystem.

## Redo?

Låt ås dyka in i Python!