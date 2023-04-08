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