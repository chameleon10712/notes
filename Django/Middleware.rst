Middleware
=============



Activating middleware
------------------------

- ``mysite/setting.py``

  - The order in MIDDLEWARE matters 順序很重要
  
    |
    - 各個 middleware 有 dependency 關係的，setting 裡的 order ㄧ定要對
    - Ex. ``SessionMiddleware`` ㄧ定要比 ``AuthentiactionMiddleware`` 順序更前面，因為 Authentication 需要 user session
    
    |
    - `Middleware order and layering <https://docs.djangoproject.com/en/3.1/topics/http/middleware/#middleware-order-and-layering>`_
    - `Middleware ordering <https://docs.djangoproject.com/en/3.1/ref/middleware/#middleware-ordering>`_
  
  |
  - .. code:: sh

      MIDDLEWARE = [
          'django.middleware.security.SecurityMiddleware',
          'django.contrib.sessions.middleware.SessionMiddleware',
          'django.middleware.common.CommonMiddleware',
          'django.middleware.csrf.CsrfViewMiddleware',
          'django.contrib.auth.middleware.AuthenticationMiddleware',
          'django.contrib.messages.middleware.MessageMiddleware',
          'django.middleware.clickjacking.XFrameOptionsMiddleware',
      ]






