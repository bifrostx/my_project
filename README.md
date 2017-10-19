# 项目介绍
这是一个利用 django-registration-redux 建立的一个包含注册系统的项目框架，使用了 bootstrap 及 Django Widget Tweaks 美化了部分 template
## 本项目在以下环境中测试通过
1. Python 3.5
2. Django 1.11.4
3. django-registration-redux 1.8
4. Django Widget Tweaks 1.4.1
## 如何使用
1. 安装以上环境
```
pip install django
pip install django-registration-redux
pip install django-widget-tweaks
```
2. clone 本项目
3. 修改```my_project\settings.py```
```
# registration settings
REGISTRATION_OPEN = True        # 是否开放注册
ACCOUNT_ACTIVATION_DAYS = 7     # 激活码有效时间
REGISTRATION_AUTO_LOGIN = True
LOGIN_REDIRECT_URL = '/'
REGISTRATION_DEFAULT_FROM_EMAIL = 'your_email@xxx.xxx'
EMAIL_HOST = 'smtp.xxx.xxx'     # 发送邮件的smtp服务器
EMAIL_PORT = 25                 # 发送邮件的端口号
EMAIL_HOST_USER = 'your_email@xxx.xxx'
EMAIL_HOST_PASSWORD = 'password'
```
4. 运行```python manage.py migrate```以建立数据库
## django-registration-redux 的 url 规则如下
```
^accounts/ ^activate/complete/$ [name='registration_activation_complete']
^accounts/ ^activate/resend/$ [name='registration_resend_activation']
^accounts/ ^activate/(?P<activation_key>\w+)/$ [name='registration_activate']
^accounts/ ^register/complete/$ [name='registration_complete']
^accounts/ ^register/closed/$ [name='registration_disallowed']
^accounts/ ^register/$ [name='registration_register']
^accounts/ ^login/$ [name='auth_login']
^accounts/ ^logout/$ [name='auth_logout']
^accounts/ ^password/change/$ [name='auth_password_change']
^accounts/ ^password/change/done/$ [name='auth_password_change_done']
^accounts/ ^password/reset/$ [name='auth_password_reset']
^accounts/ ^password/reset/complete/$ [name='auth_password_reset_complete']
^accounts/ ^password/reset/done/$ [name='auth_password_reset_done']
^accounts/ ^password/reset/confirm/(?P<uidb64>[0-9A-Za-z_\-]+)/(?P<token>.+)/$ [name='auth_password_reset_confirm']
```
**注意：本项目仅自定义了部分 templates**
