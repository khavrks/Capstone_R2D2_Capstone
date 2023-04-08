Our project has 60000 lines of code and 5 different programs that were created during this time so it is very hard to explain everything in a few paragraphs. So we will try to give you an overview of our project and how we got there. We will try to explain the different parts of our project and how they work together. As some code not even loaded to github and some of the code we think should be private we only showing the code snippets that would give you good overview of our project. In the end we will show you the end result and how you can use it.
# Table of Contents
1. [Overview](#overview)
2. [Getting Started](#getting-started)
3. [Structure](#structure)
4. [Code](#code)
5. [End Result](#end-result)
6. [Conclusion](#conclusion)
7. [References](#references)
# Overview
###### Webserver is using [Django](https://www.djangoproject.com/) as a mian framework and on top of it we use different libriries and dependencies to execute it  
- [React](https://react.dev/) build our frontend
- [Rest Framework](https://www.django-rest-framework.org/) build our api
- [All Auth](https://django-allauth.readthedocs.io/en/latest/) for authentication
- [Channels](https://channels.readthedocs.io/en/stable/) for websockets
- [PostgreSQL](https://www.postgresql.org/) for our database
- [Redis](https://redis.io/) for our cache
- [Docker](https://www.docker.com/) for our container
- [Nginx](https://www.nginx.com/) for our webserver
- [Gunicorn](https://gunicorn.org/) for our wsgi
- [Certbot](https://certbot.eff.org/) for our ssl
- [Letsencrypt](https://letsencrypt.org/) for our ssl
- [AWS](https://aws.amazon.com/) for our hosting
- [Git](https://git-scm.com/) for our version control

## React App Structure
<img src="https://bnz06pap003files.storage.live.com/y4mCw2KLVqt6VnFDR-0wh69GIj4A_H59FS5d1lOOyIY1-b_zH8sGo9qFQdivvaURxC9D_Z_Bl5pSpn_clgiukmbswgd5NYC8tD-H8YEh1TLo-kI-6mrGILJNhPWFsYE4hzn_Pru7kKJBLRhKakH4h0UV1DRV6schnWxwO9tlu8jA0Bo5q2TFm5UGEkcSbY__x3m?width=1280&height=493&cropmode=none" width="1280" height="493" />
## Structure
this is our code structure
```powershell
    ├── administrator
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-310.pyc
│   │   ├── admin.cpython-310.pyc
│   │   ├── apps.cpython-310.pyc
│   │   ├── models.cpython-310.pyc
│   │   ├── urls.cpython-310.pyc
│   │   └── views.cpython-310.pyc
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   ├── __init__.py
│   │   └── __pycache__
│   │       └── __init__.cpython-310.pyc
│   ├── models.py
│   ├── templates
│   │   └── administrator
│   │       ├── accounts
│   │       │   ├── login.html
│   │       │   └── register.html
│   │       ├── home
│   │       │   ├── api-view.html
│   │       │   ├── billing.html
│   │       │   ├── index.html
│   │       │   ├── page-403.html
│   │       │   ├── page-404.html
│   │       │   ├── page-500.html
│   │       │   ├── profile.html
│   │       │   ├── rtl.html
│   │       │   ├── sign-in.html
│   │       │   ├── sign-up.html
│   │       │   ├── tables.html
│   │       │   └── virtual-reality.html
│   │       ├── includes
│   │       │   ├── fixed-plugin.html
│   │       │   ├── footer-fullscreen.html
│   │       │   ├── footer-rtl.html
│   │       │   ├── footer.html
│   │       │   ├── navigation-fullscreen.html
│   │       │   ├── navigation-rtl.html
│   │       │   ├── navigation.html
│   │       │   ├── scripts.html
│   │       │   ├── sidebar-rtl.html
│   │       │   └── sidebar.html
│   │       └── layouts
│   │           ├── base-fullscreen.html
│   │           ├── base-rtl.html
│   │           └── base.html
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── auth_api
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-310.pyc
│   │   ├── admin.cpython-310.pyc
│   │   ├── apps.cpython-310.pyc
│   │   ├── models.cpython-310.pyc
│   │   ├── serializers.cpython-310.pyc
│   │   ├── urls.cpython-310.pyc
│   │   └── views.cpython-310.pyc
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   ├── __init__.py
│   │   └── __pycache__
│   │       └── __init__.cpython-310.pyc
│   ├── models.py
│   ├── serializers.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── backend
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-310.pyc
│   │   ├── admin.cpython-310.pyc
│   │   ├── apps.cpython-310.pyc
│   │   ├── models.cpython-310.pyc
│   │   ├── serializers.cpython-310.pyc
│   │   ├── urls.cpython-310.pyc
│   │   ├── utils.cpython-310.pyc
│   │   └── views.cpython-310.pyc
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   ├── 0001_initial.py
│   │   ├── 0002_tags_alter_video_video_streamer_view_count_and_more.py
│   │   ├── 0003_channel_preview_channel_tags_channel_title_and_more.py
│   │   ├── 0004_channel_is_live.py
│   │   ├── 0005_category_socialmedia_alter_channel_channel_name_and_more.py
│   │   ├── 0006_socialmedia_user.py
│   │   ├── 0007_remove_socialmedia_name_socialmedia_social_media_and_more.py
│   │   ├── 0008_channel_language.py
│   │   ├── 0009_channelchat.py
│   │   ├── __init__.py
│   │   └── __pycache__
│   │       ├── 0001_initial.cpython-310.pyc
│   │       ├── 0002_tags_alter_video_video_streamer_view_count_and_more.cpython-310.pyc
│   │       ├── 0003_channel_preview_channel_tags_channel_title_and_more.cpython-310.pyc
│   │       ├── 0004_channel_is_live.cpython-310.pyc
│   │       ├── 0005_category_socialmedia_alter_channel_channel_name_and_more.cpython-310.pyc
│   │       ├── 0006_socialmedia_user.cpython-310.pyc
│   │       ├── 0007_remove_socialmedia_name_socialmedia_social_media_and_more.cpython-310.pyc
│   │       ├── 0008_channel_language.cpython-310.pyc
│   │       ├── 0009_channelchat.cpython-310.pyc
│   │       └── __init__.cpython-310.pyc
│   ├── models.py
│   ├── serializers.py
│   ├── static
│   │   └── backend
│   │       ├── images
│   │       │   ├── dick.png
│   │       │   └── placeholder.png
│   │       └── placeholder.png
│   ├── tests.py
│   ├── urls.py
│   ├── utils.py
│   └── views.py
├── db.sqlite3
├── frontend
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-310.pyc
│   │   ├── admin.cpython-310.pyc
│   │   ├── apps.cpython-310.pyc
│   │   ├── consumers.cpython-310.pyc
│   │   ├── forms.cpython-310.pyc
│   │   ├── models.cpython-310.pyc
│   │   ├── routing.cpython-310.pyc
│   │   ├── urls.cpython-310.pyc
│   │   ├── utils.cpython-310.pyc
│   │   └── views.cpython-310.pyc
│   ├── admin.py
│   ├── apps.py
│   ├── babel.config.json
│   ├── consumers.py
│   ├── forms.py
│   ├── migrations
│   │   ├── __init__.py
│   │   └── __pycache__
│   │       └── __init__.cpython-310.pyc
│   ├── models.py
│   ├── package-lock.json
│   ├── package.json
│   ├── routing.py
│   ├── src
│   │   ├── App.js
│   │   ├── components
│   │   │   ├── AllCompaniesGrid.js
│   │   │   ├── BestPlacesInTheCity.js
│   │   │   ├── CafeFooter.js
│   │   │   ├── Cardgrid.js
│   │   │   ├── CategoryMenu.js
│   │   │   ├── Css
│   │   │   │   ├── Cards.css
│   │   │   │   ├── blinkCss.css
│   │   │   │   ├── cards.css
│   │   │   │   ├── subs.css
│   │   │   │   └── videoPlayer.css
│   │   │   ├── FilterBy
│   │   │   │   └── FilterComponent.js
│   │   │   ├── FilterByCompanies.js
│   │   │   ├── FilterMenu.js
│   │   │   ├── MailChimpCafe.js
│   │   │   ├── MainFooter.js
│   │   │   ├── MenuBar.js
│   │   │   ├── RestorantListing.js
│   │   │   ├── SiteBreadCrumbs.js
│   │   │   ├── SitePignation.js
│   │   │   ├── VideoCard.js
│   │   │   ├── Websocket
│   │   │   │   ├── Chat.js
│   │   │   │   └── Websocket.js
│   │   │   ├── bestplacecomponents
│   │   │   │   ├── BestPlaceByMonth.js
│   │   │   │   └── FormBestClub.js
│   │   │   ├── componentscss.css
│   │   │   ├── footercomponents
│   │   │   │   ├── Company.js
│   │   │   │   ├── NeedHelp.js
│   │   │   │   ├── Settings.js
│   │   │   │   └── Support.js
│   │   │   ├── front_ui
│   │   │   │   ├── CategoryGrid.js
│   │   │   │   ├── GamesSubscribtions.js
│   │   │   │   ├── StreamerChat.js
│   │   │   │   ├── StreamerInfo.js
│   │   │   │   ├── StreamerJoinRow.js
│   │   │   │   └── Subsribtions.js
│   │   │   ├── loginform.js
│   │   │   ├── notifications
│   │   │   │   └── SmallSaveNotification.js
│   │   │   ├── search
│   │   │   │   └── SeacrhMainPage.js
│   │   │   ├── signupform.js
│   │   │   ├── streamer_info
│   │   │   │   ├── StreamerBasicInfo.js
│   │   │   │   ├── StreamerWidget.js
│   │   │   │   ├── StreamerWidgets.js
│   │   │   │   └── SubscribeToStreamer.js
│   │   │   └── video
│   │   │       ├── VideoJS.js
│   │   │       └── VideoPlayer.js
│   │   ├── hooks
│   │   │   └── http.hook.js
│   │   ├── index.js
│   │   ├── reportWebVitals.js
│   │   ├── routs
│   │   │   ├── AllCompanies.js
│   │   │   ├── First_m3u8.js
│   │   │   ├── FrontPage.js
│   │   │   ├── HowToUse.js
│   │   │   ├── LoginPage.js
│   │   │   ├── Main.js
│   │   │   ├── SettingsUser.js
│   │   │   ├── SignUpPage.js
│   │   │   ├── StreamerPage.js
│   │   │   ├── Test_User_Page.js
│   │   │   ├── UserStream.js
│   │   │   └── landingPage.js
│   │   └── routsweb.js
│   ├── static
│   │   ├── administrator
│   │   │   └── css
│   │   │       ├── dark-theme-core.css
│   │   │       ├── dark-theme-core.css.map
│   │   │       ├── nucleo-svg.css
│   │   │       ├── nucleoicons.css
│   │   │       ├── soft-ui-dashboard.css
│   │   │       ├── soft-ui-dashboard.css.map
│   │   │       └── soft-ui-dashboard.min.css
│   │   └── frontend
│   │       ├── 131.js
│   │       ├── css
│   │       │   ├── bootstrap.css
│   │       │   ├── fontawesome.css
│   │       │   ├── fontawsemeall.css
│   │       │   ├── fontawsome40.css
│   │       │   ├── forms.css
│   │       │   └── loginForm.css
│   │       ├── main.js
│   │       ├── main.js.LICENSE.txt
│   │       ├── node_modules_web-vitals_dist_web-vitals_js.js
│   │       └── node_modules_web-vitals_dist_web-vitals_js.js.LICENSE.txt
│   ├── tests.py
│   ├── urls.py
│   ├── utils.py
│   ├── views.py
│   └── webpack.config.js
├── manage.py
├── package-lock.json
├── package.json
├── stream
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-310.pyc
│   │   ├── admin.cpython-310.pyc
│   │   ├── apps.cpython-310.pyc
│   │   └── models.cpython-310.pyc
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   ├── __init__.py
│   │   └── __pycache__
│   │       └── __init__.cpython-310.pyc
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── streaming_app
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-310.pyc
│   │   ├── asgi.cpython-310.pyc
│   │   ├── settings.cpython-310.pyc
│   │   ├── urls.cpython-310.pyc
│   │   └── wsgi.cpython-310.pyc
│   ├── asgi.py
│   ├── celery.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── templates
    ├── account
    │   ├── account_inactive.html
    │   ├── base.html
    │   ├── email
    │   │   ├── base_message.txt
    │   │   ├── email_confirmation_message.txt
    │   │   ├── email_confirmation_signup_message.txt
    │   │   ├── email_confirmation_signup_subject.txt
    │   │   ├── email_confirmation_subject.txt
    │   │   ├── password_reset_key_message.txt
    │   │   ├── password_reset_key_subject.txt
    │   │   ├── unknown_account_message.txt
    │   │   └── unknown_account_subject.txt
    │   ├── email.html
    │   ├── email_confirm.html
    │   ├── login.html
    │   ├── logout.html
    │   ├── messages
    │   │   ├── cannot_delete_primary_email.txt
    │   │   ├── email_confirmation_sent.txt
    │   │   ├── email_confirmed.txt
    │   │   ├── email_deleted.txt
    │   │   ├── logged_in.txt
    │   │   ├── logged_out.txt
    │   │   ├── password_changed.txt
    │   │   ├── password_set.txt
    │   │   ├── primary_email_set.txt
    │   │   └── unverified_primary_email.txt
    │   ├── password_change.html
    │   ├── password_reset.html
    │   ├── password_reset_done.html
    │   ├── password_reset_from_key.html
    │   ├── password_reset_from_key_done.html
    │   ├── password_set.html
    │   ├── signup.html
    │   ├── signup_closed.html
    │   ├── snippets
    │   │   └── already_logged_in.html
    │   ├── verification_sent.html
    │   └── verified_email_required.html
    ├── administrator
    │   ├── accounts
    │   │   ├── login.html
    │   │   └── register.html
    │   ├── home
    │   │   ├── api-view.html
    │   │   ├── billing.html
    │   │   ├── index.html
    │   │   ├── page-403.html
    │   │   ├── page-404.html
    │   │   ├── page-500.html
    │   │   ├── profile.html
    │   │   ├── rtl.html
    │   │   ├── sign-in.html
    │   │   ├── sign-up.html
    │   │   ├── tables.html
    │   │   └── virtual-reality.html
    │   ├── includes
    │   │   ├── fixed-plugin.html
    │   │   ├── footer-fullscreen.html
    │   │   ├── footer-rtl.html
    │   │   ├── footer.html
    │   │   ├── navigation-fullscreen.html
    │   │   ├── navigation-rtl.html
    │   │   ├── navigation.html
    │   │   ├── scripts.html
    │   │   ├── sidebar-rtl.html
    │   │   └── sidebar.html
    │   └── layouts
    │       ├── base-fullscreen.html
    │       ├── base-rtl.html
    │       └── base.html
    ├── frontend
    │   ├── index.html
    │   ├── login.html
    │   └── register.html
    ├── main
    │   └── layout.html
    ├── openid
    │   ├── base.html
    │   └── login.html
    └── socialaccount
        ├── authentication_error.html
        ├── base.html
        ├── connections.html
        ├── login.html
        ├── login_cancelled.html
        ├── messages
        │   ├── account_connected.txt
        │   ├── account_connected_other.txt
        │   ├── account_connected_updated.txt
        │   └── account_disconnected.txt
        ├── signup.html
        └── snippets
            ├── login_extra.html
            └── provider_list.html
```
 
this is our main settings that we used in our project 
```python
CSRF_TRUSTED_ORIGINS = ['https://r2d2streaming.site']

SITE_URL = 'https://r2d2streaming.site'

URL_FRONT = 'https://r2d2streaming.site'

DEFAULT_HTTP_PROTOCOL = 'https'

INSTALLED_APPS = [

    # mine
    'backend',
    'frontend',
    'administrator',
    'stream',
    'auth_api',
    'channels',
    'channels_redis',

    # pip install
    'corsheaders',
    'rest_framework',
    'storages',
    'django_filters',
    'captcha',
    'allauth',
    'allauth.account',
    'allauth.socialaccount',
    'allauth.socialaccount.providers.google',
    'allauth.socialaccount.providers.telegram',
    'allauth.socialaccount.providers.vk',
    "django_cron",
    'crispy_forms',
    "crispy_bootstrap5",
    "phonenumber_field",
    'rest_framework_simplejwt',
    'rest_framework_simplejwt.token_blacklist',
    'rest_framework.authentication',

    # django
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    #extra 
    'django.contrib.sites',
]

MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',

    #extra
    "corsheaders.middleware.CorsMiddleware",
    "django.middleware.common.CommonMiddleware",
]

ROOT_URLCONF = 'streaming_app.urls'

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [BASE_DIR / 'templates'],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

ASGI_APPLICATION = 'streaming_app.asgi.application'


CHANNEL_LAYERS = {
"default": {
"BACKEND": "channels_redis.core.RedisChannelLayer",
"CONFIG": {
"hosts": [("localhost", 6379)],
},
},
}

# Database
# https://docs.djangoproject.com/en/4.1/ref/settings/#databases

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'streaming_server',
        'USER': 'stream',
        'PASSWORD': '**********,
        'HOST': 'localhost',
        'PORT': '5432',
    }
}



# Password validation
# https://docs.djangoproject.com/en/4.1/ref/settings/#auth-password-validators

AUTH_PASSWORD_VALIDATORS = [
    {
        'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
    },
]

AUTHENTICATION_BACKENDS = [
    # Needed to login by username in Django admin, regardless of `allauth`
    'django.contrib.auth.backends.ModelBackend',

    # `allauth` specific authentication methods, such as login by e-mail
    'allauth.account.auth_backends.AuthenticationBackend',
]

ACCOUNT_ADAPTER = "allauth.account.adapter.DefaultAccountAdapter"
ACCOUNT_SIGNUP_FORM_CLASS = 'frontend.forms.UserFormSignUp'

ACCOUNT_EMAIL_REQUIRED = True
ACCOUNT_EMAIL_VERIFICATION = False
ACCOUNT_SESSION_REMEMBER = True
```

API urls 
```python
from django.urls import path
from . import views


urlpatterns = [
    path('', views.index, name='index'),
    path('is_authenticated/', views.is_authenticated.as_view(),
        name='is_authenticated'),
    path('test_video_stream/<str:stream_id>',
        views.test_video_stream.as_view(), name='test_video_stream'),
    path('getViewerCount/<str:stream_id',views.getviewerCount.as_view(),name='stream_view_count'),
    path('getStreamerUrls/<str:streamer_id>', views.getStreamerUrls.as_view(), name='getStreamerUrls'),
    path('subscribe/<str:channel_name>', views.SubscribeToChannel.as_view(), name='subscribe'),
    path('unsubscribe/<str:channel_name>', views.UnSubscribeToChannel.as_view(), name='unsubscribe'),
    path('getStreamPreview/<str:channel_name>', views.GetVideoStreamPreview.as_view(), name='getStreamPreview'),
    path('getStreamersInfo/<str:channel_name>', views.GetStreamersInfo.as_view(), name='getStreamersInfo'),
    path('getLiveStreamers/', views.GetLiveStreamers.as_view(), name='getLiveStreamers'),
    path('getStreamersByRaiting/', views.GetStreamersSortByRaiting.as_view(), name='getStreamers'),
    path('getStreamersByViews/', views.GetStreamersSortByViews.as_view(), name='getStreamers'),
    path('getStreamersByTags/<str:tag>', views.GetStreamersSortByTags.as_view(), name='getStreamers'),
    path('getLiveStreamersByRating/', views.GetLiveStreamersSortByRaiting.as_view(), name='getLiveStreamers'),
    path('getSreamerInfo/<str:channel_name>', views.GetSreamerInfo.as_view(), name='GetSreamerInfo'),
    path('getUserStreamerInfo/', views.GetUserStreamerInfo.as_view(), name='GetUserStreamerInfo'),
    path('subscribeToChannel/<str:channel_name>', views.SubscribeToChannel.as_view(), name='subscribeToChannel'),
    path('unSubscribeToChannel/<str:channel_name>', views.UnSubscribeToChannel.as_view(), name='unSubscribeToChannel'),
    path('getSubscriptions/', views.GetSubscriptions.as_view(), name='getSubscriptions'),
    path('isUserAStreamer/<str:channel_name>', views.IsUserAStreamer.as_view(), name='IsUserAStreamer'),
    path('userSubsribedToChannel/<str:channel_name>', views.UserSubsribedToChannel.as_view(), name='UserSubsribedToChannel'),
    path('settingsStreamer/<str:channel_name>', views.SettingsStreamer.as_view(), name='SettingsStreamer'),
    path('privateKey/<str:channel_name>', views.PrivateKey.as_view(), name='PrivateKey'),
    path('changePrivateKey/<str:channel_name>', views.ChangePrivateKey.as_view(), name='ChangePrivateKey'),
    path('setStreamerTodayStream/<str:channel_name>', views.SetStreamerTodayStream.as_view(), name='SetStreamerTodayStream'),
    path('getCategories/', views.GetCategories.as_view(), name='GetCategories'),
    path('seacrhChannels/<str:search>', views.SeacrhChannels.as_view(), name='SeacrhChannels'),
    path('getStreamsChat/<str:channel_name>', views.GetStreamsChat.as_view(), name='GetStreamsChat'),
    path('setStreamerImages/<str:channel_name>', views.SetStreamerImages.as_view(), name='SetStreamerImages'),
    path('get_user/', views.GetUser.as_view(), name='get_user'),
    path('getStreamerLanguage/<str:channel_name>', views.GetStreamerLanguage.as_view(), name='GetStreamerLanguage'),
]
```


API example 
```python
from urllib import response
from django.http import HttpResponse
from django.shortcuts import render
from rest_framework import generics, status
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework.parsers import MultiPartParser, FormParser
from requests import Request, Session, get, session
from django.core.files.storage import FileSystemStorage
from rest_framework.authentication import SessionAuthentication, BasicAuthentication
from rest_framework.permissions import IsAuthenticated
from rest_framework.decorators import api_view, authentication_classes, permission_classes
import time
import asyncio

from frontend.utils import make_private_key
from .models import *
from .serializers import *
from dynamodb_json import json_util as dynamodb_json
import boto3

from .utils import *

class SetStreamerImages(APIView):
        
        parser_classes = (MultiPartParser, FormParser)
        
        def get(self, request, channel_name):
            ch = Channel.objects.get(channel_name=channel_name)
            serializer = ChannelImagesSerializer(ch)
            return Response(serializer.data, status=status.HTTP_200_OK)
    
        def post(self, request, channel_name):
            usr = request.user
            print(request.data)
            try:
                ch = Channel.objects.get(channel_name=channel_name, user=usr)
                serializer = ChannelImagesSerializer(ch, data=request.data)
                if serializer.is_valid():
                    serializer.save()
                    return Response(serializer.data, status=status.HTTP_200_OK)
                return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)
            except Exception as e:
                return Response({"erroes": e.args} ,status=status.HTTP_400_BAD_REQUEST)    
```

webscokets connection 
```python
import json
from channels.generic.websocket import WebsocketConsumer
from asgiref.sync import async_to_sync
from datetime import datetime
from backend.models import Channel
from backend.models import ChannelChat
from django.contrib.auth.models import User

class ChatConsumer(WebsocketConsumer):

    def connect(self):
        self.stream_id = self.scope['url_route']['kwargs']['stream_id']
        async_to_sync(self.channel_layer.group_add)(str(self.stream_id), self.channel_name)
        self.channel_stream = Channel.objects.get(channel_name=self.stream_id)
        self.channel_stream.views += 1
        self.is_live = self.channel_stream.is_live
        self.channel_stream.save()
        async_to_sync(self.channel_layer.group_send)(str(self.stream_id), {'type': 'live_status', 'is_live': self.is_live})
        async_to_sync(self.channel_layer.group_send)(
            str(self.stream_id), {'type': 'view_count', 'views': self.channel_stream.views}
        )
        self.accept()
```

main channel model 
```python
class Channel(models.Model):
    private_key = models.CharField(max_length=100)
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    bio = models.TextField(max_length=200, null=True, blank=True)
    channel_name = models.CharField(max_length=25, validators=[MinLengthValidator(3)], unique=True)
    channel_image = models.ImageField(upload_to='channel_images', null=True, blank=True)
    channel_cover = models.ImageField(upload_to='channel_covers', null=True, blank=True)
    thumbnail = models.ImageField(upload_to='thumbnails', null=True, blank=True)
    created_at = models.DateTimeField(auto_now_add=True)
    channel_rating = models.IntegerField(default=0)
    title = models.CharField(max_length=100, null=True, blank=True)
    views = models.IntegerField(default=0, null=True, blank=True)
    tags = models.ManyToManyField(Tags, blank=True)
    preview = models.ImageField(upload_to='previews', null=True, blank=True)
    is_live = models.BooleanField(default=False)
    social_media_urls = models.ManyToManyField(SocialMedia, blank=True)
    category = models.ForeignKey(Category, on_delete=models.CASCADE, null=True, blank=True)
    language = models.CharField(max_length=100, choices=LANGUAGE_CHOICES, default='English')
    # widjets = models.TextField(max_length=1000, null=True, blank=True)

    def __str__(self):
        return self.channel_name

    class Meta:
        ordering = ['-created_at']
        verbose_name = 'Channel'
        verbose_name_plural = 'Channels'
```

frontend login required example
```python
@login_required
def settingsusr(request, channel_name):
    ch = Channel.objects.get(channel_name=channel_name)
    if request.user != ch.user:
        return redirect('main')
    context = {'segment': 'settings', 'content_type': "application/x-javascript"}
    html_template = loader.get_template('frontend/index.html')
    return HttpResponse(html_template.render(context, request))
```

main page of the application 
```javascript
import React, {useEffect, useState} from "react";
import { Col, Container, Row } from "react-bootstrap";
import {CardGrid} from "../components/Cardgrid";
import {CategoryGrid} from "../components/front_ui/CategoryGrid";

import { useHttp } from '../hooks/http.hook';



export const FrontPage = () => {

    const {loading, request} = useHttp();

    const [live_streams, setLive_streams] = useState([]);
    const [streams_by_raiting, setStreams_by_raiting] = useState([]);
    const [streamer_info, setStreamer_info] = useState([]);
    const [categories, setCategories] = useState([]);

    const getLiveStreams = async () => {
        const data = await request('/api/getLiveStreamers/', 'GET');
        setLive_streams(data);
    }

    const getStreamersByRaiting = async () => {
        const data = await request('/api/getStreamersByRaiting/', 'GET');
        setStreams_by_raiting(data);
    }

    const getCategories = async () => {
        const data = await request('/api/getCategories/', 'GET');
        setCategories(data);
        console.log(data);
    }


    useEffect(() => {
        getLiveStreams();
        getStreamersByRaiting();
        getCategories();
    }, [])


    return (
        <div>
            <h2>
                Live Streams
            </h2>
           <CardGrid stream_name={live_streams} />
           <CategoryGrid categorys_name={categories} />
           <CardGrid stream_name={streams_by_raiting} />
        </div>
    )
}
```
