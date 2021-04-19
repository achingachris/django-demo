# Adding Static files to Django

CSS, images and js files are referred to as static files in django. It's now more than easier to configure them into your project, in just simple steps.

I will use the files from the previous article on how to start a django project to show demo setup process. 

It's an easy process, TL;DR

On your django project, or using the repo, :

open the project's settings.py, at the bottom notice:

```python
STATIC_URL = '/static/'
```

By default that covers for the static files configurations.

# CSS

To test that out, create a static folder on your app diectory. and add a `style.css` file.

add an easily noticable style, say background color:

```css
main {
    background-color: black;
    color: white;
}
```

then head over to your template and import the styles:

first of all we need to inform django that the template will be using statis files using the following line:

```HTML
{% load static %}
```

add it at the top of the page.


normally, we'd import the styles using this format:

```HTML
    <link rel="stylesheet" href="style.css">
```

it's slighlty different when using django:

```HTML
    <link rel="stylesheet" href="{% static 'style.css' %}">
```

## JS

adding javascript files is same.

back to the static folder, create a js file: `script.js`

add a simple script:

```javascript
console.log('Congratulations, javscript is loaded and working')
```

import the script to your template:

```html
    <script src="{% static 'script.js' %}"></script>
```

## Images

add any image on your static folder:

loading images would be simple:

## buyaa, you are all set to go...
next: using templates in django