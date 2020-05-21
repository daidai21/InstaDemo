# Jiuzhang Django Course Demo

### Install & Running

```sh
git clone https://github.com/daidai21/InstaDemo
pipenv install
pipenv shell
python manage.py makemigrations Insta
python manage.py migrate
python manage.py runserver
# nohup python manage.py runserver& >> django.log  # daemon process and backup log
# exit  # quit pipenv virtualenv
```

### Create superuser admin

`python manage.py createusperuser`

`admin` - `123456`

### QA

```text
***** like点赞问题 *****
index.js里面的url改为  url: '/insta/like/',
InstaDemo/urls.py中的url改为  path('insta/', include('Insta.urls')),
Insta/urls.py中的url改为  path('like/', addLike, name='addLike'),
```
