Views
========

Introduction to class-based views
-----------------------------------

The relationship and history of generic view, class-based views, and class-based generic views
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

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




|

Reference

- `Introduction to class-based views <https://docs.djangoproject.com/en/3.1/topics/class-based-views/intro/>`_

|

Class-based views
---------------------

A view is a callable which takes a request and returns a response.
This can be more than just a function, and Django provides an example of some classes which can be used as views.
These allow you to structure your views and reuse code by harnessing inheritance and mixins. 







