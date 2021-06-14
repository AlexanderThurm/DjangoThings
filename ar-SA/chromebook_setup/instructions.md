يمكنك [تخطي هذا القسم ](http://tutorial.djangogirls.org/en/installation/#install-python) إذا كنت لا تستخدم كروم بوك. إذا كنت كذلك، تجربة التثبيت الخاص بك سوف تكون مختلفة قليلاً. يمكنك تجاهل بقية إرشادات التثبيت.

### بيئة التطوير المتكاملة السحابية (PaizaCloud Cloud IDE, AWS Cloud9)

بيئة التطوير المتكاملة السحابية هي أداة توفر لك تحرير الأكواد البرمجية والوصول إلى جهاز كمبيوتر يعمل على شبكة الإنترنت حيث يمكنك تثبيت، وكتابة، وتشغيل البرامج. خلال مدة البرنامج التعليمي، بيئة التطوير المتكاملة السحابية ستكون بمثابة *الجهاز المحلي* الخاص بك. سوف تقوم بتنفيذ الأوامر في موجه الأوامر مثل زملائك الذين يعملون على أنظمة OS X, Ubuntu, أو Windows, لكن موجه الأوامر في السحابة سيكون متصل بجهاز حاسوبي يعمل في مكان اخر تقوم بيئة التطوير المتكاملة السحابية بإعداده لك. وإليك الإرشادات الخاصة ببيئات التطوير المتكاملة السحابية (PaizaCloud Cloud IDE, AWS Cloud9). يمكنك اختيار إحدى بيئات التطوير المتكاملة السحابية، واتباع تعليمات بيئة التطوير المتكاملة السحابية.

#### بيئة التطوير المتكاملة السحابية PaizaCloud

1. الذهاب إلى [PaizaCloud Cloud IDE](https://paiza.cloud/)
2. إنشاء حساب جديد
3. إنشاء خادم بالضغط على *New Server* واختيار Django
4. الضغط على زر Terminal (على الجانب الأيسر من النافذة)

الآن سترى واجهة مع قائمة جانبية، وأزرار على اليسار. اضغطي زر "Terminal" لفتح نافذة موجه الأوامر مثل هذا:

{% filename %} Terminal{% endfilename %}

    $
    

موجه الأوامر في PaizaCloud IDE مستعد لأوامرك. يمكنك تغيير حجم النافذة أو تكبيرها لجعلها أكبر قليلاً.

#### AWS Cloud9

حالياً Cloud 9 تتطلب تسجيلك في AWS وإدخال معلومات بطاقتك البنكية.

1. ثبت Cloud 9 من [ متجر كروم](https://chrome.google.com/webstore/detail/cloud9/nbdmccoknlfggadpfkmcpnamfnbkmkcp)
2. إذهب الى [c9.io](https://c9.io) واضغط على *ابدأ مع AWS Cloud9*
3. أنشئ حساب في AWS (يتطلب معلومات بطاقتك البنكية، لكن تستطيع استخدامها مجاناً)
4. من AWS Dashboard، أدخل *Cloud9* في مربع البحث ثم اضغطه
5. من Cloud 9 dashboard، اضغط *Create environment*
6. سمه *django-girls*
7. أثناء تعديل الإعدادات، من "Environment Type" اختر *Create a new instance for environment (EC2)*، ومن "Instance type" اختر *t2.micro*. (المفترض يظهر لك "Free-tier eligible." أي أنها متوفرة في الفئة المجانية). إعدادات cost-saving الافتراضية لا بأس بها، وتستطيع إبقاء الإعدادات الافتراضية الأخرى على ما هي عليه.
8. اضغط على *Next step*
9. اضغط *Create environment*

الآن يفترض أن تشاهد واجهة وقائمة جانبية، ونافذة رئيسية كبيرة تحتوي نص، ونافذة صغيرة في الجزء السفلي التي تبدو مثل هذا:

{% filename %}bash{% endfilename %}

    yourusername:~/workspace $
    

هذه المساحة السفلية تحتوي موجه الأوامر الخاص بك. يمكنك استخدام موجه الأوامر لإرسال التعليمات إلى الكمبيوتر البعيد في Cloud 9. يمكنك تغيير حجم تلك النافذة لجعلها أكبر قليلاً.

#### معرف Glitch.com السحابي

1. انتقل إلى [Glitch.com](https://glitch.com/)
2. قم بالتسجيل للحصول على حساب (https://glitch.com/signup) أو استخدم حساب GitHub الخاص بك إذا كان لديك حساب. (انظر تعليمات GitHub أدناه)
3. انقر فوق *New Project* واختر *hello-webpage*
4. Click on the Tools dropdown list (at the bottom left side of the window), then on Terminal button to open terminal tab with a prompt like this:

{% filename %}Terminal{% endfilename %}

    app@name-of-your-glitch-project:~
    

عند استخدام Glitch.com كقاعدة بيانات سحابية، لا تحتاج إلى إنشاء بيئة افتراضية. بدلاً من ذلك، قم بإنشاء الملفات التالية يدوياً:

{% filename %}glitch.json{% endfilename %}

```json
{
  "install": "pip3 install -r requirements.txt --user",
  "start": "bash start.sh",
  "watch": {
    "throttle": 1000
  }
}
```

{% filename %}requirements.txt{% endfilename %}

    Django~={{ book.django_version }}
    

{% filename %}.bash_profile{% endfilename %}

```bash
alias python=python3
alias pip=pip3
```

{% filename %}start.sh{% endfilename %}

```bash
chmod 600 .bash_profile
pip3 install -r requirements.txt --user
python3 manage.py makemigrations
python3 manage.py migrate
python3 manage.py runserver $PORT
```

Once these files are created, go to the Terminal and execute the following commands to create your first Django project:

{% filename %}Terminal{% endfilename %}

    django-admin.py startproject mysite .
    refresh
    

In order to see detailed error messages, you can activate Django debug logs for your Glitch application. Simply add the following at the end of the `mysite/settings.py` file.

{% filename %}mysite/settings.py{% endfilename %}

```python
LOGGING = {
    'version': 1,
    'disable_existing_loggers': False,
    'handlers': {
        'file': {
            'level': 'DEBUG',
            'class': 'logging.FileHandler',
            'filename': 'debug.log',
        },
    },
    'loggers': {
        'django': {
            'handlers': ['file'],
            'level': 'DEBUG',
            'propagate': True,
        },
    },
}
```

This will create a `debug.log` file detailing Django operations and any error messages that might come up, making it much easier to fix if your website does not work.

The initial restarting of the Glitch project should fail. (If you click on the top dropdown button `Show` then click on `In a New Window`, you will receive a `DisallowedHost` error message.) Do not worry about it at this stage, the tutorial will fix this as soon as you update the Django settings of your project in the `mysite/settings.py` file.

### البيئة الافتراضية

A virtual environment (also called a virtualenv) is like a private box we can stuff useful computer code into for a project we're working on. We use them to keep the various bits of code we want for our various projects separate so things don't get mixed up between projects.

تشغيل:

{% filename %}Cloud 9{% endfilename %}

    mkdir djangogirls
    cd djangogirls
    python3 -m venv myvenv
    source myvenv/bin/activate
    pip install django~={{ book.django_version }}
    

(note that on the last line we use a tilde followed by an equal sign: `~=`).

### GitHub

Make a [GitHub](https://github.com) account.

### بايثون في كل مكان

The Django Girls tutorial includes a section on what is called Deployment, which is the process of taking the code that powers your new web application and moving it to a publicly accessible computer (called a server) so other people can see your work.

This part is a little odd when doing the tutorial on a Chromebook since we're already using a computer that is on the Internet (as opposed to, say, a laptop). However, it's still useful, as we can think of our Cloud 9 workspace as a place for our "in progress" work and Python Anywhere as a place to show off our stuff as it becomes more complete.

Thus, sign up for a new Python Anywhere account at [www.pythonanywhere.com](https://www.pythonanywhere.com).