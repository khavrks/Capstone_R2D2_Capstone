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


###### code 

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