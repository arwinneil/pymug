# pymug
website source of pymug.com - python mauritius user group

NOTE: As noted on fb and linked-in, joining our groups on social media adds you as a member on our website. Joining our groups is about commitment to Python. A personal page is created for you with your skills listed. It shows at the very least the path to learn py.

# Website
https://pymug.github.io/pymug/ or http://www.pymug.com

# Structure
the site's structure is dictated by github pages' specifications and handling rather than good standards.

an index.html in every folder, path or lib, is a brillant idea of github (really). See tutorial section below

# Activating Vitual env

**Windows:**

Activate (from pymug/):

```
cd pymug-web/scripts/ & activate & cd ..\..
```

or just type

```
win_vactivate
```

Deactivate:

```
cd pymug-web/scripts/ & deactivate & cd ..\..
```

or just type

```
win_vdeactivate
```

# Installing dependencies

```
pip install -r requirements.txt
```

# Quick start

run build.py to build

# Add yourself as a member

open an issue with your name,username,date in the format

name / username / date

or open a Pull Request and add your name to the bottom of the file [here](https://github.com/pymug/pymug/blob/master/docs/data/members_basic/members.txt)

# Python version 

3.7

# Tutorial

The website has two folders the `templates/` folder and the output folder, here `docs/`. `data/` folder is used to store data used by `build.py`. 

### Building `index.html` (main page)

The story begins with the `sections` variable in `build.py`:

```python
sections = {
    'events': {
        'link': 'events.html',
        'fa_class': 'fa-calendar'
    },
    'news': {
        'link': 'news.html',
        'fa_class': 'fa-newspaper-o'
    },
    'members': {
        'link': 'members_basic.html',
        'fa_class': 'fa-angle-up'
    }, ...
}
```

This is used to generate the different sections icons. `link` specifies where on clicking they should go and `fa_class` is the FontAwesome (4.7) class used. FontAwesome is an icon library which includes icons by specifying the appropriate class.

### The build process

Towards the end of `build.py` you'll see

```python
def build_all():
    build_main_page()
    build_members_basic()
    build_register()
    build_about()
    build_pystandard()
    build_blog()
    build_business()
    build_members_hon()
    build_news()
    build_social()
    build_resources()
    build_partners()
    build_events()
    build_maintainers()
    build_codeoc()
    build_all_members()


if __name__ == '__main__':
    build_all()
```

where each function in `build_all()` builds a section. `build_events()` for example builds `pymug.com/events.html`
