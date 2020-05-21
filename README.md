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

***** 'AnonymousUser' object is not iterable *****
在Insta/views.py里面的PostListView的get_queryset开头加上
>>> if not self.request.user.is_authenticated:
>>>     return 
先要验证用户是否登陆，再执行接下来的步骤
```

### TODO

- [ ] show followers / following list
