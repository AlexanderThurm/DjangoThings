> هذا القسم يستند على دورة تعليمية من فتيات الجزر المهووسات (https://github.com/ggcarrots/django-carrots).
> 
> جزء من هذا القسم يستند [django-marcador tutorial](http://django-marcador.keimlink.de/) المرخص لها بمرخصة بموجب المشاع الإبداعي   إسناد-على غرار 4.0 الترخيص الدولي. البرنامج التعليمي django-marcador حقوق الطبع والنشر من قبل Markus Zapke-Gründemann وآخرون.

## البيئة الافتراضية

قبل تنصيب دجانغو ، سوف نقوم بتنصيب اداة جد مهمة وستساعدنا كثيرا،في الحفاظ على بيئة كتابة التعليمات البرمجية الخاصة بك مرتبة على جهاز الكمبيوتر. من الممكن تخطي هذه الخطوة، ولكن نحن يوصي بشدة بها. بدءاً من الإعداد الأفضل والذي سيحميك من الكثير من المتاعب في المستقبل!

هيا لننشئ **بيئة افتراضية** ، تسمى ايضا ب *virtualenv*. سوف تعزل البيئة الإفتراضية إعدادات بايثون / دجانغو الخاص بك على أساس كل مشروع. وهذا يعني أن أية تغييرات تقوم بإجرائها على موقع واحد لن تؤثر على المواقع الأخرى التي تطورها. أنيق، أليس كذالك؟

كل ما عليك القيام به هو العثور على الدليل الذي تريد إنشاء `virtualenv`؛ فيه الدليل الرئيسي الخاص بك، على سبيل المثال. في Windows قد تبدو مثل `C:\Users\Name` (حيث `Name` هو اسم تسجيل الدخول الخاص بك).

> **ملاحظة:** في Windows، تأكد من أن هذا الدليل لا يحتوي على أحرف هجائية أو خاصة؛ إذا كان اسم المستخدم الخاص بك يحتوي على أحرف هجائية، استخدام دليل مختلف، على سبيل المثال `C:\djangogirls`.

في هذا البرنامج التعليمي سوف نستخدم دليل جديد `djangogirls` من الدليل الرئيسي الخاص بك:

{% filename %}command-line{% endfilename %}

    $ mkdir djangogirls
    $ cd djangogirls
    

سوف نقوم بإنشاء بيئة افتراضية تسمى `myvenv`. سوف تكون القيادة العامة في التنسيق:

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

<!--sec data-title="Virtual environment: Windows" data-id="virtualenv_installation_windows"
data-collapse=true ces-->

لإنشاء `virtualenv`, جديد، تحتاج إلى فتح موجه الأوامر وتشغيل `python -m venv myvenv`. وسوف تبدو كما يلي:

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls> python -m venv myvenv
    

حيث `myvenv` هو اسم خاص ب `virtualenv`. يمكنك استخدام أي اسم آخر، لكن حافض على الحروف الصغيرة ولا تستخدم مسافات أو لهجات أو أحرف خاصة. كما أنها فكرة جيدة الحفاظ على الاسم قصير – سوف تستخدمه كمرجع كثيرا!

<!--endsec-->

<!--sec data-title="Virtual environment: Linux and OS X" data-id="virtualenv_installation_linuxosx"
data-collapse=true ces-->

يمكننا إنشاء `virtualenv` على لينكس ونظام التشغيلOS X عن طريق تشغيل `python3 -m venv myvenv`:

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

حيث `myvenv` هو اسم خاص ب `virtualenv`. يمكنك استخدام أي اسم آخر، لكن حافض على الحروف الصغيرة ولا تستخدم مسافات. كما أنها فكرة جيدة الحفاظ على الاسم قصير – سوف تستخدمه كمرجع كثيرا!

> **ملاحظة:** في بعض الإصدارات من ديبيان/أوبونتو قد تتلقى الخطأ التالي:
> 
> {% filename %}command-line{% endfilename %}
> 
>     لم يتم إنشاء البيئة الإفتراضية بنجاح لأن ensurepip غير متوفر.  على أنظمة ديبيان/أوبونتو، تحتاج إلى تثبيت حزمة python3-venv باستخدام الأمر التالي.
>        apt-get install python3-venv
>     غالبا ستحتاج إستعمال sudo لتنفيد الأمر.  بعد تثبيت حزمة python3-venv، قم بإعادة إنشاء البيئة الإفتراضية الخاصة بك.
>     
> 
> في هذه الحالة اتبع التعليمات تحت وثبت حزمة `python3-venv` {% filename %}command-line{% endfilename %}
> 
>     $ sudo apt install python3-venv
>     
> 
> **ملاحظة:** في بعض إصدارات ديبيان/أوبونتو اعداد البيئة الإفتراضية بهذه الطريقة قد يعطي هذا الخطأ:
> 
> {% filename %}command-line{% endfilename %}
> 
>     Error: Command '['/home/eddie/Slask/tmp/venv/bin/python3', '-Im', 'ensurepip', '--upgrade', '--default-pip']' returned non-zero exit status 1
>     
> 
> للالتفاف على هذا، استخدم الأمر `virtualenv` بدلاً من ذلك.
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ sudo apt install python-virtualenv
>     $ virtualenv --python=python{{ book.py_version }} myvenv
>     
> 
> **ملاحظة:** إذا حصلت على خطأ مثل
> 
> {% filename %}command-line{% endfilename %}
> 
>     E: Unable to locate package python3-venv
>     
> 
> قم بتنفيد الأمر:
> 
> {% filename %}command-line{% endfilename %}
> 
>     sudo apt install python{{ book.py_version }}-venv
>     

<!--endsec-->

## العمل مع virtualenv

الأمر أعلاه سينشئ دليل يسمى `myvenv` (أو أيا كان الاسم الذي تختاره) الذي يحتوي على بيئتنا الإفتراضية (أساسا حفنة من الدلائل والملفات).

<!--sec data-title="Working with virtualenv: Windows" data-id="virtualenv_windows"
data-collapse=true ces-->

بدء تشغيل البيئة الإفتراضية الخاصة بك عن طريق تشغيل:

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls> myvenv\Scripts\activate
    

> **ملاحظة:** على Windows 10 قد تحصل على خطأ في Windows PowerShell يقول `execution of scripts is disabled on this system`. وفي هذه الحالة، قم بفتح Windows PowerShell آخر باستخدام الخيار "تشغيل كمسؤول". ثم حاول كتابة الأمر التالي قبل تشغيل البيئة الإفتراضية الخاصة بك:
> 
> {% filename %}command-line{% endfilename %}
> 
>     C:\WINDOWS\system32> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
>         Execution Policy Change
>         The execution policy helps protect you from scripts that you do not trust. تغيير سياسة التنفيذ قد يعرضك للمخاطر الأمنية الموضحة في موضوع التعليمات about_Execution_Policies في http://go.microsoft.com/fwlink/?LinkID=135170. هل تريد تغيير نهج التنفيذ؟ [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): A
>     

<!-- (This comment separates the two blockquote blocks, so that GitBook and Crowdin don't merge them into a single block.) -->

> **ملاحظة:** لمستخدمي المحرر الشائع VS Code، الذي يأتي مع محطة طرفية متكاملة مبنية من windows PowerShell، إذا كنت ترغب في التمسك بالمحطة الطرفية المدمجة، فيمكنك تشغيل الأمر التالي لتفعيل البيئة الافتراضية الخاصة بك:
> 
>     $ . myvenv\Scripts\activate.ps1
>     
> 
> الميزة هي أنه ليس عليك التبديل بين نوافذ المحرر ونوافذ سطر الأوامر

<!--endsec-->

<!--sec data-title="Working with virtualenv: Linux and OS X" data-id="virtualenv_linuxosx"
data-collapse=true ces-->

ابدأ بيئتك الافتراضية بتشغيل:

{% filename %}command-line{% endfilename %}

    $ source myvenv/bin/activate
    

تذكر أن تستبدل `myvenv` باسم `virtualenv` الذي اخترته!

> **ملاحظة:** في بعض الأحيان قد يكون `source` غير متوفر. وفي تلك الحالات حاول القيام بهذا بدلاً من ذلك:
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ . myvenv/bin/activate
>     

<!--endsec-->

سوف تعرف أنك قمت بتفعيل الـ `virtualenv` الخاصة بك عندما ترى أن الموجه في وحدة التحكم الخاصة بك مسبوقاً بـ `(myvenv)`.

عند العمل ضمن بيئة افتراضية، سيشير `python` تلقائياً إلى الإصدار الصحيح حيث يمكنك استخدام `python` بدلاً من `python3`.

حسنا، لدينا كافة التبعيات الهامة في المكان. وأخيراً يمكننا تثبيت جانغو!

## تثبيت جانغو {#django}

الآن بما انه لديك `virtualenv` مشغل، يمكنك تثبيت جانغو.

قبل أن نفعل ذلك، يجب علينا التأكد من لدينا أحدث إصدار من `pip`، البرامج التي نستخدمها لتثبيت جانغو:

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ python -m pip install --upgrade pip
    

### تثبيت الحزم مع المتطلبات

ملف المتطلبات يحتفظ بقائمة من التبعيات ليتم تثبيتها باستخدام `pip install`:

أولاً قم بإنشاء ملف `requirements.txt` داخل مجلد `djangogirls` باستخدام محرر التعليمات البرمجية الذي قمت بتثبيته سابقاً. تفعل ذلك عن طريق فتح ملف جديد في محرر التعليمات البرمجية وحفظه بإسم `requirements.txt` في مجلد `djangogirls/` سيبدو الدليل الخاص بك هكذا:

    djangogirls
    ├── myvenv
    │   └── ...
    └───requirements.txt
    

في ملف `djangogirls/requirements.txt` يجب عليك إضافة النص التالي:

{% filename %}djangogirls/requirements.txt{% endfilename %}

    Django~={{ book.django_version }}
    

الآن، قم بتشغيل `pip install -r requirements.txt` لتثبيت جانغو.

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ pip install -r requirements.txt
    Collecting Django~={{ book.django_version }} (from -r requirements.txt (line 1))
      Downloading Django-{{ book.django_version }}-py3-none-any.whl (7.1MB)
    Installing collected packages: Django
    Successfully installed Django-{{ book.django_version }}
    

<!--sec data-title="Installing Django: Windows" data-id="django_err_windows"
data-collapse=true ces-->

> إذا كنت تحصل على خطأ عند استدعاء برنامج pip على منصة Windows، الرجاء التحقق إذا كان اسم مسار المشروع الخاص بك يحتوي على مسافات أو علامات نطقية أو أحرف خاصة (على سبيل المثال، `C:\Users\User Name\djangogirls`). إذا كان كذالك، يرجى التفكير في استخدام مكان آخر دون مسافات، علامات نطقية أو أحرف خاصة (اقتراح: `C:\djangogirls`). أنشئ virtualenv جديدة في الدليل الجديد، ثم إحذف القديمة وحاول تنفيذ الأمر أعلاه مرة أخرى. (نقل دليل virtualenv لن يعمل لأن virtualenv يستخدم مسارات مطلقة.)

<!--endsec-->

<!--sec data-title="Installing Django: Windows 8 and Windows 10" data-id="django_err_windows8and10"
data-collapse=true ces-->

> قد يجمد سطر الأوامر الخاص بك بعد أن تحاول تثبيت جانغو. إذا حدث ذلك، فبدلا من استخدام الأمر أعلاه:
> 
> {% filename %}command-line{% endfilename %}
> 
>     C:\Users\Name\djangogirls> python -m pip install -r requirements.txt
>     

<!--endsec-->

<!--sec data-title="Installing Django: Linux" data-id="django_err_linux"
data-collapse=true ces-->

> إذا كنت تحصل على خطأ عند استدعاء برنامج pip على أوبونتو 12.04 الرجاء تشغيل `python -m pip install -U --force-reinstall pip` لإصلاح تثبيت برنامج pip في virtualenv.

<!--endsec-->

هذا كل شيء! أنت الآن على استعداد لإنشاء تطبيق جانغو (أخيرا)!