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

ordinary user:

```
username: a ~ e
password: 12345qwert12345
```

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

***** django-imagekit *****
这个包安装的时候配置的路径或者环境变量的问题，就在本地环境和当前的虚拟环境都使用`pip install django-imagekit`或者`pip3 install django-imagekit`安装这个库

***** Python环境问题 *****
在Shell中分别执行`python -V`, `python3 -V`, `pip -V`, `pip3 -V`，查看结果
查看Python 3对应的pip版本，记住是pip还是pip3，后面使用这个安装lib

***** vscode自动补全问题 *****
安装自动补全和语法检查之类的vscode插件就好，尝试：jinja、Better Jinja、Python Template Snippets等插件
```

### TODO

- [x] show followers / following list
