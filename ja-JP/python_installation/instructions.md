> 家で１人でこのチャプターに挑戦している方へ：この章は、動画（英語）もあるので参考にしてください。 [Installing Python & Code Editor](https://www.youtube.com/watch?v=pVTaqzKZCdA)
> 
> このセクションはGeek Girls Carrots (https://github.com/ggcarrots/django-carrots) のチュートリアルをベースに作成しました。

DjangoはPythonで書かれています。 Djangoを使うにはPythonが必要です。 では、インストールするところから始めましょう！ 最新のPython３をインストールしてください。それ以前のPythonがインストールされていたら、アップグレードする必要があります。 もしあなたが{{ book.py_min_version }}かそれ以上のバージョンを持っているのなら大丈夫です。

下に書いたとおりのやり方で、Pythonをインストールしてください。すでにAnacondaが入っていても以下のとおりにインストールしてください。

<!--sec data-title="Install Python: Windows" data-id="python_windows" data-collapse=true ces-->

まず、今使っているWindowsが32-bit版か64-bit版か確認しましょう。システム情報の”システムの種類”を確認してください。これを見る方法はいくつかあるので、次のうち１つをやってみましょう：

* WindowsキーとPause/Breakキーを同時に押します。
* Windowsのスタートからコントロールパネルを開き、”システムとセキュリティ”、”システム”と順にクリックします。
* Windowsロゴをクリック、設定 > システム > バージョン情報 とクリックしていきましょう。
* Windowsのスタートメニューから「システムの詳細設定」を検索します。 これを行うためには、スタートのボタンをクリックするかWindowsキーを押して、`システムの詳細設定`を入力し始めます。 入力するとすぐに候補を提案します。 表示されたら、選択することができます。

https://www.python.org/downloads/windows/ からWindows版のPythonをダウンロードできます。 "Latest Python 3 Release - Python x.x.x" というリンクをクリックします。 あなたのWindowsが**64-bit版**なら、**Windows x86-64 executable installer**をダウンロードしてください。 そうでなければ**Windows x86 executable installer**をダウンロードしてください。 インストーラーがダウンロードできたら、ダブルクリックして実行し、指示に従ってください。

インストールの途中で、「Setup」というタイトルのウィンドウがでてきたら注意してください。 以下に書かれてあるように（インストールしているバージョンが違った場合は表示されている内容が少し異なるかもしれません）、"Python {{ book.py_version }} to PATH" か "Add Python to your environment variables" のチェックボックスをチェックし、"Install Now"をクリックします。

![Pythonのパスを通すのを忘れないようにしてください。](../python_installation/images/python-installation-options.png)

インストールが終わったら、ダイアログボックスが出てきます。ボックス内のリンクを開くと、Pythonやインストールしたバージョンを説明したページに行けます。 ダイアログは閉じてしまいましょう。Pythonの使い方はこのチュートリアルでたっぷり勉強します！

注意: もしあなたが古いバージョンのWindows(7, Vistaなど)使用している場合、Python {{ book.py_version }} インストーラーはエラーを起こし失敗します。Windowsアップデートをインストールし再度Pythonをインストールしてください。 もしもエラーが起こり続けているのなら、Python バージョン {{ book.py_min_release }} を[Python.org](https://www.python.org/downloads/windows/)からダウンロードしてみてください。

> Django {{ book.django_version }} はWindows XP以前のバージョンがサポートしていない Python {{ book.py_min_version }} 以上のバージョンを必要とします。

<!--endsec-->

<!--sec data-title="Install Python: OS X" data-id="python_OSX"
data-collapse=true ces-->

> **注意** OS X にPython をインストールする前に、Mac の設定がApp Store以外からのパッケージのインストールを許可しているか確認してください。 Go to System Preferences (it's in the Applications folder), click "Security & Privacy," and then the "General" tab. If your "Allow apps downloaded from:" is set to "Mac App Store," change it to "Mac App Store and identified developers."

You need to go to the website https://www.python.org/downloads/mac-osx/ and download the latest Python installer:

* *Mac OS X 64-bit/32-bit installer* というファイルをダウンロードします。 
* Double click *python-{{ book.py_release }}-macosx10.9.pkg* to run the installer.

<!--endsec-->

<!--sec data-title="Install Python: Linux" data-id="python_linux"
data-collapse=true ces-->

おそらく殆どの場合は、すでに Python をインストールしていると思います。Python をインストールしているか確認するために（またどのばーじょんかかを）、コンソールを開いて以下のコマンドをうってください。

{% filename %}command-line{% endfilename %}

    $ python3 --version
    Python {{ book.py_release }}
    

異なるバージョンの Python をインストールしている場合、少なくとも{{ book.py_min_version }} （例: {{ book.py_min_release }}）、アップグレードの必要はありません。 Pythonがインストールされていなかったり、異なるバージョンをインストールしたい場合は、はじめに下記のコマンドでどの Linux ディストリビューションを使っているか確認してください。

{% filename %}command-line{% endfilename %}

    $ grep '^NAME=' /etc/os-release
    

Afterwards, depending on the result, follow one of the following installation guides below this section.

<!--endsec-->

<!--sec data-title="Install Python: Debian or Ubuntu" data-id="python_debian" data-collapse=true ces-->

Type this command into your console:

{% filename %}command-line{% endfilename %}

    $ sudo apt install python3
    

<!--endsec-->

<!--sec data-title="Install Python: Fedora" data-id="python_fedora"
data-collapse=true ces-->

Use this command in your console:

{% filename %}command-line{% endfilename %}

    $ sudo dnf install python3
    

If you're on older Fedora versions you might get an error that the command `dnf` is not found. In that case, you need to use `yum` instead.

<!--endsec-->

<!--sec data-title="Install Python: openSUSE" data-id="python_openSUSE"
data-collapse=true ces-->

Use this command in your console:

{% filename %}command-line{% endfilename %}

    $ sudo zypper install python3
    

<!--endsec-->

Verify the installation was successful by opening a command prompt and running the `python3` command:

{% filename %}command-line{% endfilename %}

    $ python3 --version
    Python {{ book.py_release }}
    

The version shown may be different from {{ book.py_release }} -- it should match the version you installed.

**NOTE:** If you're on Windows and you get an error message that `python3` wasn't found, try using `python` (without the `3`) and check if it still might be a version of Python that is {{ book.py_min_version }} or higher. If that doesn't work either, you may open a new command prompt and try again; this happens if you use a command prompt left open from before the Python installation.

* * *

If you have any doubts, or if something went wrong and you have no idea what to do next, please ask your coach! Sometimes things don't go smoothly and it's better to ask for help from someone with more experience.