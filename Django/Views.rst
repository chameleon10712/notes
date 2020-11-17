Views
========

Django provides base view classes which will suit a wide range of applications. All views inherit from the `View <https://docs.djangoproject.com/en/3.1/ref/class-based-views/base/#django.views.generic.base.View>`_ class, which handles linking the view into the URLs, HTTP method dispatching and other common features. `RedirectView <https://docs.djangoproject.com/en/3.1/ref/class-based-views/base/#django.views.generic.base.RedirectView>`_ provides a HTTP redirect, and `TemplateView <https://docs.djangoproject.com/en/3.1/ref/class-based-views/base/#django.views.generic.base.TemplateView>`_ extends the base class to make it also render a template.


|

Introduction to class-based views
-----------------------------------

The relationship and history of generic view, class-based views, and class-based generic views


- function-based views

  - cover the simple cases well, but no way to extend or customize


- class-based generic views

  - built for maximum flexibility, too complicate for simplest use cases


- class-based views

|

Using class-based views
+++++++++++++++++++++++++++

- view function

.. code:: python

  from django.http import HttpResponse

  def my_view(request):
      if request.method == 'GET':
          # <view logic>
          return HttpResponse('result')



- class-based views

.. code:: python

  from django.http import HttpResponse
  from django.views import View

  class MyView(View):
      def get(self, request):
          # <view logic>
          return HttpResponse('result')



- ``as_view()`` classmethod

  - Because Django’s URL resolver expects to send the request and associated arguments to a callable function, not a class, class-based views have an `as_view() <https://docs.djangoproject.com/en/3.1/ref/class-based-views/base/#django.views.generic.base.View.as_view>`_ class method which returns a function that can be called when a request arrives for a URL matching the associated pattern. 
  
    .. code:: python

        # urls.py
        from django.urls import path
        from myapp.views import MyView

        urlpatterns = [
            path('about/', MyView.as_view()),
        ]


|


Using mixins
++++++++++++++++

Mixins are a form of multiple inheritance where behaviors and attributes of multiple parent classes can be combined.


- `Docs - Using mixins <https://docs.djangoproject.com/en/3.1/topics/class-based-views/intro/#using-mixins>`_




|

Reference

- `Introduction to class-based views <https://docs.djangoproject.com/en/3.1/topics/class-based-views/intro/>`_

|

Class-based views
---------------------

A view is a callable which takes a request and returns a response.
This can be more than just a function, and Django provides an example of some classes which can be used as views.
These allow you to structure your views and reuse code by harnessing inheritance and mixins. 







