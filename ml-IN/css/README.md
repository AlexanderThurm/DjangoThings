# CSS - നമ്മുക് അത് മനോഹരമാക്കാം!

നമ്മുടെ ബ്ലോഗ് ഇപ്പോഴും കാണാന്‍ വലിയ ഭംഗിയില്ല, അല്ലേ? അത് ഭംഗിയാക്കാന്‍ സമയമായി! അതിനു വേണ്ടി നമുക്കു CSS ഉപയോഗിക്കാം.

## എന്താണ് CSS?

Cascading Style Sheets (CSS) is a language used for describing the look and formatting of a website written in a markup language (like HTML). Treat it as make-up for our web page. ;)

But we don't want to start from scratch again, right? Once more, we'll use something that programmers released on the Internet for free. Reinventing the wheel is no fun, you know.

## നമുക്ക് Bootstrap ഉപയോഗിക്കാം!

Bootstrap is one of the most popular HTML and CSS frameworks for developing beautiful websites: https://getbootstrap.com/

It was written by programmers who worked for Twitter. Now it's developed by volunteers from all over the world!

## Bootstrap ഇന്‍സ്റ്റാള്‍ ചെയ്യാം

To install Bootstrap, open up your `.html` file in the code editor and add this to the `<head>` section:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
```

This doesn't add any files to your project. It just points to files that exist on the Internet. So go ahead, open your website and refresh the page. Here it is!

![Figure 14.1](images/bootstrap1.png)

ഇപ്പോള്‍ തന്നെ ഒന്നു ഭംഗി കൂടിയില്ലേ!

## Django-യിലെ static ഫൈലുകള്‍

ഒടുവില്‍ നമ്മള്‍ **static ഫൈലുകള്‍** എന്നു വിളിച്ചുകൊണ്ടിരിക്കുന്ന ഈ വസ്തുക്കളെ ഒന്നു പരിഷോധിക്കാം. Static files are all your CSS and images. Their content doesn't depend on the request context and will be the same for every user.

### Django-യിലെ static ഫൈലുകള്‍ എവിടെ വെക്കണം

Django already knows where to find the static files for the built-in "admin" app. Now we need to add some static files for our own app, `blog`.

അത് ചെയ്യാനായി നമുക്ക് blog ആപ്പിനകത്ത് ഒരു `static` എന്ന് പേരുള്ള ഫോള്‍ഡര്‍ നിര്‍മിക്കാം:

    djangogirls
    ├── blog
    │   ├── migrations
    │   ├── static
    │   └── templates
    └── mysite
    

Django will automatically find any folders called "static" inside any of your apps' folders. Then it will be able to use their contents as static files.

## നമ്മുടെ ആദ്യത്തെ CSS ഫൈല്‍!

Let's create a CSS file now, to add your own style to your web page. `css` എന്ന് പേരുള്ള ഒരു പുതിയ ടയറക്ട്റി നിങ്ങളുടെ `static` ടയറക്ട്റിക്കകത്ത് നിര്‍മിക്കൂ. എന്നിട്ട് `blog.css` എന്ന് പേരുള്ള ഒരു പുതിയ ഫൈല്‍ ഈ `css` ടയറക്ടറിക്കകത്ത് നിര്‍മിക്കൂ. Ready?

    djangogirls
     └─── blog
          └─── static
               └─── css
                    └─── blog.css
    

കുറച്ച് CSS എഴുതാന്‍ നേരമായി! നിങ്ങളുടെ ടെക്സ്ട് എഡിറ്ററില്‍ `blog/static/css/blog.css` എന്ന ഫൈല്‍ തുറക്കൂ.

We won't be going too deep into customizing and learning about CSS here. There is a recommendation for a free CSS course at the end of this page if you would like to learn more.

എന്നാലും നമുക്ക് കുറച്ചൊന്ന് ചെയ്തു നോക്കാം. Maybe we could change the color of our headers? നിറങ്ങളെ മനസ്സിലാക്കുവാനായി കംബ്യൂട്ടറുകള്‍ പ്രത്യേക കോഡുകള്‍ ഉപയോഗിക്കും. These codes start with `#` followed by 6 letters (A–F) and numbers (0–9). For example, the code for blue is `#0000FF`. You can find the color codes for many colors here: http://www.colorpicker.com/. നേരിട്ട് നിറങ്ങളുടെ പേരുകള്‍ ഉപയോഗിച്ചാലും തെറ്റില്ല. ഉദാഹരണത്തിന് `red` എന്നോ `green` എന്നോ ഉപയോഗിക്ക.

നിങ്ങളുടെ `blog/static/css/blog.css` ഫൈലില്‍ താഴെ കാണിച്ചിട്ടുള്ള കോട് ചേര്‍ക്കുക:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
h1 a, h2 a {
    color: #C25100;
}

```

`h1 a`-നെ ഒരു CSS Selector എന്നണ് വിളിക്കുക. This means we're applying our styles to any `a` element inside of an `h1` element; the `h2 a` selector does the same thing for `h2` elements. So when we have something like `<h1><a href="">link</a></h1>`, the `h1 a` style will apply. In this case, we're telling it to change its color to `#C25100`, which is a dark orange. Or you can put your own color here, but make sure it has good contrast against a white background!

ഒരു HTML ഫൈലിലുള്ള എലമെന്റ്സിന്റെ സ്ടൈലിനെയാണ് നമ്മള്‍ ഒരു CSS ഫൈലില്‍ നിര്‍ണയിക്കുന്നത്. The first way we identify elements is with the element name. You might remember these as tags from the HTML section. Things like `a`, `h1`, and `body` are all examples of element names. We also identify elements by the attribute `class` or the attribute `id`. Class-ഉം id-യും നിങ്ങള്‍ തന്നെ എലമെന്റ്സിനു കൊടുക്കുന്ന പേരുകളാണ്. ഒരു class ഒരു കൂട്ടം എലമെന്റ്സിനെ വര്‍ണ്ണിക്കുവാന്‍ ഉപയോഗിക്കുന്നതാണ്. എന്നാല്‍ ഒരു id ഒരു പ്രത്യേഗ എലമെന്റിനെയാണ് സൂജിപ്പിക്കുന്നത്. For example, you could identify the following element by using the element name `a`, the class `external_link`, or the id `link_to_wiki_page`:

```html
<a href="https://en.wikipedia.org/wiki/Django" class="external_link" id="link_to_wiki_page">
```

You can read more about [CSS Selectors at w3schools](http://www.w3schools.com/cssref/css_selectors.asp).

We also need to tell our HTML template that we added some CSS. Open the `blog/templates/blog/post_list.html` file in the code editor and add this line at the very beginning of it:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% load static %}
```

We're just loading static files here. :) Between the `<head>` and `</head>` tags, after the links to the Bootstrap CSS files, add this line:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link rel="stylesheet" href="{% static 'css/blog.css' %}">
```

The browser reads the files in the order they're given, so we need to make sure this is in the right place. Otherwise the code in our file may be overriden by code in Bootstrap files. നമ്മുടെ CSS ഫൈല്‍ എവിടെയാണെന്ന് നമ്മുടെ ടെംപ്ലൈറ്റിനോട് നാം പറഞ്ഞുകൊടുത്ത് കഴിഞ്ഞു.

നമ്മുടെ ഫൈല്‍ കണ്ടാല്‍ താഴെ കൊടുത്തിട്ടുളളത് പോലെ ഇരിക്കണം:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% load static %}
<!DOCTYPE html>
<html>
    <head>
        <title>Django Girls blog</title>
        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
        <link rel="stylesheet" href="{% static 'css/blog.css' %}">
    </head>
    <body>
        <header>
            <h1><a href="/">Django Girls Blog</a></h1>
        </header>

        {% for post in posts %}
            <article>
                <time>published: {{ post.published_date }}</time>
                <h2><a href="">{{ post.title }}</a></h2>
                <p>{{ post.text|linebreaksbr }}</p>
            </article>
        {% endfor %}
    </body>
</html>
```

ഫൈല്‍ സേവ് ചെയത് സൈറ്റ് റിഫ്രഷ് ചെയ്യൂ!

![Figure 14.2](images/color2.png)

അടിപൊളി! നമ്മുടെ വെബ്സൈറ്റിന് എടതു ഭാഗത്തെ മാര്‍ജിന്‍ കൂട്ടി ഇത്തിരി വിസ്താരം നല്‍കാം? ശ്രമിക്കാം!

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
body {
    padding-left: 15px;
}
```

Add that to your CSS, save the file and see how it works!

![Figure 14.3](images/margin2.png)

നമ്മുടെ ഹെഡറിന്റെ ഫോണ്ടില്‍ ഒരു ഭേതഗതി വരുത്തി നോക്കിയാലോ? നിങ്ങളുടെ `blog/templates/blog/post_list.html` എന്ന ഫൈലിലെ `<head>`-ലോട്ട് താഴെയുള്ളത് പേസ്റ്റ് ചെയ്യൂ:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<link href="//fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext" rel="stylesheet" type="text/css">
```

As before, check the order and place before the link to `blog/static/css/blog.css`. This line will import a font called *Lobster* from Google Fonts (https://www.google.com/fonts).

Find the `h1 a` declaration block (the code between braces `{` and `}`) in the CSS file `blog/static/css/blog.css`. Now add the line `font-family: 'Lobster';` between the braces, and refresh the page:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
h1 a, h2 a {
    color: #C25100;
    font-family: 'Lobster';
}
```

![Figure 14.3](images/font.png)

ഉഷാര്‍!

As mentioned above, CSS has a concept of classes. These allow you to name a part of the HTML code and apply styles only to this part, without affecting other parts. This can be super helpful! Maybe you have two divs that are doing something different (like your header and your post). A class can help you make them look different.

Go ahead and name some parts of the HTML code. Replace the `header` that contains your header with the following:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<header class="page-header">
    <div class="container">
        <h1><a href="/">Django Girls Blog</a></h1>
    </div>
</header>
```

And now add a class `post` to your `article` containing a blog post.

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<article class="post">
    <time>published: {{ post.published_date }}</time>
    <h2><a href="">{{ post.title }}</a></h2>
    <p>{{ post.text|linebreaksbr }}</p>
</article>
```

We will now add declaration blocks to different selectors. Selectors starting with `.` relate to classes. There are many great tutorials and explanations about CSS on the Web that can help you understand the following code. For now, copy and paste it into your `blog/static/css/blog.css` file:

{% filename %}blog/static/css/blog.css{% endfilename %}

```css
.page-header {
    background-color: #C25100;
    margin-top: 0;
    margin-bottom: 40px;
    padding: 20px 20px 20px 40px;
}

.page-header h1,
.page-header h1 a,
.page-header h1 a:visited,
.page-header h1 a:active {
    color: #ffffff;
    font-size: 36pt;
    text-decoration: none;
}

h1,
h2,
h3,
h4 {
    font-family: 'Lobster', cursive;
}

.date {
    color: #828282;
}

.save {
    float: right;
}

.post-form textarea,
.post-form input {
    width: 100%;
}

.top-menu,
.top-menu:hover,
.top-menu:visited {
    color: #ffffff;
    float: right;
    font-size: 26pt;
    margin-right: 20px;
}

.post {
    margin-bottom: 70px;
}

.post h2 a,
.post h2 a:visited {
    color: #000000;
}

.post > .date,
.post > .actions {
    float: right;
}

.btn-default,
.btn-default:visited {
    color: #C25100;
    background: none;
    border-color: #C25100;
}

.btn-default:hover {
    color: #FFFFFF;
    background-color: #C25100;
}
```

Then surround the HTML code which displays the posts with declarations of classes. Replace this:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% for post in posts %}
    <article class="post">
        <time>published: {{ post.published_date }}</time>
        <h2><a href="">{{ post.title }}</a></h2>
        <p>{{ post.text|linebreaksbr }}</p>
    </article>
{% endfor %}
```

in the `blog/templates/blog/post_list.html` with this:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<main class="container">
    <div class="row">
        <div class="col">
            {% for post in posts %}
                <article class="post">
                    <time class="date">
                        {{ post.published_date }}
                    </time>
                    <h2><a href="">{{ post.title }}</a></h2>
                    <p>{{ post.text|linebreaksbr }}</p>
                </article>
            {% endfor %}
        </div>
    </div>
</main>
```

Save those files and refresh your website.

![Figure 14.4](images/final.png)

Woohoo! Looks awesome, right? Look at the code we just pasted to find the places where we added classes in the HTML and used them in the CSS. Where would you make the change if you wanted the date to be turquoise?

Don't be afraid to tinker with this CSS a little bit and try to change some things. Playing with the CSS can help you understand what the different things are doing. If you break something, don't worry – you can always undo it!

We really recommend taking the free online courses "Basic HTML & HTML5" and "Basic CSS" on [freeCodeCamp](https://learn.freecodecamp.org/). They can help you learn all about making your websites prettier with HTML and CSS.

Ready for the next chapter?! :)