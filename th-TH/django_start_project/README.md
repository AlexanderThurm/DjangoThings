# Django project แรก ของคุณ!

> บางส่วนของบทนี้ยึดหลักจากบทเรียนของ Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).
> 
> บางส่วนของบทนี้ยึดหลักจาก [django-marcador tutorial](http://django-marcador.keimlink.de/) ที่ได้รับอนุญาตภายใต้ Creative Commons Attribution-ShareAlike 4.0 International License บทเรียน django-marcador เป็นลิขสิทธิ์ของ Markus Zapke-Gründemann

เราจะมาสร้างบล็อกแบบง่ายๆ กัน!

ขั้นตอนแรกคือการสร้าง Django project ใหม่ โดยทั่วไปแล้ว เราจะทำการเรียกใช้สคริปต์บางอย่างที่มาพร้อมกับ Django ซึ่งจะทำการสร้างโครงของ project Django ให้กับเรา ซึ่งประกอบไปด้วย ไฟล์และไดเรกทอรีจำนวนหนึ่งที่เราจะใช้ต่อไป

บางชื่อในบางไฟล์และไดเรกทอรีนั้นสำคัญมากๆ สำหรับ Django และคุณไม่ควรเปลี่ยนชื่อไฟล์เหล่านั้น และการย้ายไฟล์เหล่านั้นไปยังที่อื่น ก็ไม่ใช่ความคิดที่ดีแน่ๆ Django นั้นต้องการโครงสร้างที่แน่นอน เพื่อที่จะสามารถหาสิ่งที่จำเป็นที่จะต้องใช้ได้

> อย่าลืมที่จะรันทุกสิ่งอย่างภายใต้ virtualenv If you don't see a prefix `(myvenv)` in your console, you need to activate your virtualenv. เราอธิบายวิธีทำไว้แล้วในบท **การติดตั้ง Django** อยู่ในส่วนของ **การทำงานกับ virtualenv** โดยพิมพ์ `myvenv\Scripts\activate` บน Windows หรือ `source myvenv/bin/activate` บน Mac OS หรือ บน Linux มันจะจัดการให้คุณเอง

<!--sec data-title="Create project: OS X or Linux" data-id="django_start_project_OSX_Linux" data-collapse=true ces-->

In your Mac OS X or Linux console, you should run the following command. **Don't forget to add the period (or dot) `.` at the end!**

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ django-admin startproject mysite .
    

> เครื่องหมายจุด `.` นี้ สำคัญ เพราะเป็นตัวบอกว่าให้ติดตั้ง Django ลงในไดเรกทอรีปัจจุบัน (ใช้เครื่องหมาย `.` เป็นการอ้างอิงถึงไดเรกทอรีปัจจุบันแบบลัด).
> 
> **Note** When typing the command above, remember that you only type the part which starts by `django-admin`. The `(myvenv) ~/djangogirls$` part shown here is just example of the prompt that will be inviting your input on your command line.

<!--endsec-->

<!--sec data-title="Create project: Windows" data-id="django_start_project_windows" data-collapse=true ces-->

On Windows you should run the following command. **(Don't forget to add the period (or dot) `.` at the end)**:

{% filename %}command-line{% endfilename %}

    (myvenv) C:\Users\Name\djangogirls> django-admin.exe startproject mysite .
    

> เครื่องหมายจุด `.` นี้ สำคัญ เพราะเป็นตัวบอกว่าให้ติดตั้ง Django ลงในไดเรกทอรีปัจจุบัน (ใช้เครื่องหมาย `.` เป็นการอ้างอิงถึงไดเรกทอรีปัจจุบันแบบลัด).
> 
> **Note** When typing the command above, remember that you only type the part which starts by `django-admin.exe`. The `(myvenv) C:\Users\Name\djangogirls>` part shown here is just example of the prompt that will be inviting your input on your command line.

<!--endsec-->

`django-admin.py` เป็นสคริปต์สำหรับสร้างไฟล์และไดเรกทอรีให้กับคุณ และตอนนี้คุณควรจะมีโครงสร้างไฟล์และไดเรกทอรีตามนี้:

    djangogirls
    ├── manage.py
    ├── mysite
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    ├── myvenv
    │   └── ...
    └── requirements.txt
    

> **Note**: in your directory structure, you will also see your `venv` directory that we created before.

`manage.py` is a script that helps with management of the site. With it we will be able (amongst other things) to start a web server on our computer without installing anything else.

ไฟล์ `settings.py` ประกอบไปด้วยไฟล์ที่กำหนดค่าต่างๆ ในเว็บไซต์ของคุณ

จำเกี่ยวกับคนส่งจดหมายได้ไหม? `urls.py` คือไฟล์ที่มีรายการรูปแบบที่ถูกนำไปใช้ใน `urlresolver`.

ไฟล์อื่นๆ เราไว้ว่ากันทีหลัง สิ่งสำคัญตอนนี้คือ อย่าเผลอไปลบไฟล์พวกนี้เล่นล่ะ!

## เปลี่ยนการตั้งค่า

เรามาแก้ไขไฟล์ `mysite/settings.py` กัน เปิดไฟล์นี้ด้วยโปรแกรมแก้ไขโค้ดที่คุณติดตั้งไว้แล้ว

**Note**: Keep in mind that `settings.py` is a regular file, like any other. You can open it from inside the code editor, using the "file -> open" menu actions. This should get you the usual window in which you can navigate to your `settings.py` file and select it. Alternatively, you can open the file by navigating to the djangogirls folder on your desktop and right-clicking on it. Then, select your code editor from the list. Selecting the editor is important as you might have other programs installed that can open the file but will not let you edit it.

คงจะดีไม่น้อยถ้าเว็บของเรามีการตั้งค่าเวลาที่ถูกต้อง Go to [Wikipedia's list of time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) and copy your relevant time zone (TZ) (e.g. `Europe/Berlin`).

In `settings.py`, find the line that contains `TIME_ZONE` and modify it to choose your own timezone. For example:

{% filename %}mysite/settings.py{% endfilename %}

```python
TIME_ZONE = 'Europe/Berlin'
```

A language code consist of the language, e.g. `en` for English or `de` for German, and the country code, e.g. `de` for Germany or `ch` for Switzerland. If English is not your native language, you can add this to change the default buttons and notifications from Django to be in your language. So you would have "Cancel" button translated into the language you defined here. [Django comes with a lot of prepared translations](https://docs.djangoproject.com/en/2.2/ref/settings/#language-code).

If you want a different language, change the language code by changing the following line:

{% filename %}mysite/settings.py{% endfilename %}

```python
LANGUAGE_CODE = 'de-ch'
```

We'll also need to add a path for static files. (We'll find out all about static files and CSS later in the tutorial.) Go down to the *end* of the file, and just underneath the `STATIC_URL` entry, add a new one called `STATIC_ROOT`:

{% filename %}mysite/settings.py{% endfilename %}

```python
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
```

When `DEBUG` is `True` and `ALLOWED_HOSTS` is empty, the host is validated against `['localhost', '127.0.0.1', '[::1]']`. This won't match our hostname on PythonAnywhere once we deploy our application so we will change the following setting:

{% filename %}mysite/settings.py{% endfilename %}

```python
ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']
```

> **Note**: If you're using a Chromebook, add this line at the bottom of your settings.py file: `MESSAGE_STORAGE = 'django.contrib.messages.storage.session.SessionStorage'`
> 
> Also add `.amazonaws.com` to the `ALLOWED_HOSTS` if you are using cloud9
> 
> If you are hosting your project on `Glitch.com`, let us protect the Django secret key that needs to remain confidential (otherwise, anyone remixing your project could see it):
> 
> - First, we are going to create a random secret key. Open the Glitch terminal again, and type the following command: {% filename %}.env{% endfilename %} 
>         bash
>         python -c 'from django.core.management.utils import get_random_secret_key; \
>               print(get_random_secret_key())' This should display a long random string, perfect to use as a secret key for your brand new Django web site. We will now paste this key into a 
>     
>     `.env` file that Glitch will only show you if you are the owner of the web site. 
> - Create a file `.env` at the root of your project and add the following property in it: {% filename %}.env{% endfilename %} 
>         bash
>         # Here, inside the single quotes, you can cut and paste the random key generated above
>         SECRET='3!0k#7ds5mp^-x$lqs2%le6v97h#@xopab&oj5y7d=hxe511jl'
> 
> - Then update the Django settings file to inject this secret value and set the Django web site name: {% filename %}mysite/settings.py{% endfilename %} 
>         python
>         SECRET_KEY = os.getenv('SECRET')
> 
> - And a little further, in the same file, we inject the name of your new Glitch website: {% filename %}mysite/settings.py{% endfilename %} 
>         python
>         ALLOWED_HOSTS = [os.getenv('PROJECT_DOMAIN') + ".glitch.me"] The 
>     
>     `PROJECT_DOMAIN` value is automatically generated by Glitch. It will correspond to the name of your project.

## ตั้งค่าฐานข้อมูล

มีซอฟต์แวร์ฐานข้อมูลจำนวนมากที่สามารถเก็บข้อมูลของเว็บคุณได้ เราจะใช้ฐานข้อมูลเริ่มต้น คือ `sqlite3`.

ซึ่งได้ถูกตั้งค่าไว้เรียบร้อยแล้วในไฟล์ `mysite/settings.py` ของคุณ:

{% filename %}mysite/settings.py{% endfilename %}

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```

การสร้งฐานข้อมูลสำหรับบล็อกของเรา เริ่มต้นด้วยการใช้คำสั่งต่อไปนี้ในคอนโซล: `python manage.py migrate` (เราจำเป็นต้องอยู่ไดเรกทอรี `djangogirls` ซึ่งมีไฟล์ `manage.py` อยู่ด้านใน) ถ้าทุกอย่างเป็นไปด้วยดี คุณจะเห็นผลคล้ายๆ แบบนี้:

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py migrate
    Operations to perform:
      Apply all migrations: auth, admin, contenttypes, sessions
    Running migrations:
      Rendering model states... DONE
      Applying contenttypes.0001_initial... OK
      Applying auth.0001_initial... OK
      Applying admin.0001_initial... OK
      Applying admin.0002_logentry_remove_auto_add... OK
      Applying contenttypes.0002_remove_content_type_name... OK
      Applying auth.0002_alter_permission_name_max_length... OK
      Applying auth.0003_alter_user_email_max_length... OK
      Applying auth.0004_alter_user_username_opts... OK
      Applying auth.0005_alter_user_last_login_null... OK
      Applying auth.0006_require_contenttypes_0002... OK
      Applying auth.0007_alter_validators_add_error_messages... OK
      Applying auth.0008_alter_user_username_max_length... OK
      Applying auth.0009_alter_user_last_name_max_length... OK
      Applying sessions.0001_initial... OK
    

เป็นอันเสร็จสิ้น! ได้เวลาเปิดเว็บเซิร์ฟเวอร์และดูว่าเว็บเราทำงานไหม!

## การเปิดใช้เว็บเซิร์ฟเวอร์

คุณต้องอยู่ในไดเรกทอรีที่มีไฟล์ `manage.py` (ไดเรกทอรี `djangogirls` นั่นเอง) ในคอนโซล เราสามารถเริ่มต้นเว็บเซิร์ฟเวอร์โดยรันคำสั่ง `python manage.py runserver`:

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py runserver
    

If you are on a Chromebook, use this command instead:

{% filename %}Cloud 9{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py runserver 0.0.0.0:8080
    

or this one if you are using Glitch:

{% filename %}Glitch.com terminal{% endfilename %}

    $ refresh
    
    

If you are on Windows and this fails with `UnicodeDecodeError`, use this command instead:

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py runserver 0:8000
    

Now you need to check that your website is running. Open your browser (Firefox, Chrome, Safari, Internet Explorer or whatever you use) and enter this address:

{% filename %}browser{% endfilename %}

    http://127.0.0.1:8000/
    

If you're using a Chromebook and Cloud9, instead click the URL in the pop-up window that should have appeared in the upper right corner of the command window where the web server is running. The URL will look something like:

{% filename %}browser{% endfilename %}

    https://<a bunch of letters and numbers>.vfs.cloud9.us-west-2.amazonaws.com
    

or on Glitch:

    https://name-of-your-glitch-project.glitch.me
    

Congratulations! You've just created your first website and run it using a web server! Isn't that awesome?

![Install worked!](images/install_worked.png)

Note that a command window can only run one thing at a time, and the command window you opened earlier is running the web server. As long as the web server is running and waiting for additional incoming requests, the terminal will accept new text but will not execute new commands.

> We reviewed how web servers work in the **How the Internet works** chapter.

To type additional commands while the web server is running, open a new terminal window and activate your virtualenv -- to review instructions on how to open a second terminal window, see [Introduction to the command line](../intro_to_command_line/README.md). To stop the web server, switch back to the window in which it's running and press CTRL+C - Control and C keys together (on Windows, you might have to press Ctrl+Break).

Ready for the next step? It's time to create some content!