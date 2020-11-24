Shortcuts
============

common usage

- `get_object_or_404() <https://docs.djangoproject.com/en/3.1/topics/http/shortcuts/#get-object-or-404>`_

Ex.

.. code:: py

  # polls/views.py
  from django.shortcuts import get_object_or_404, render


  def results(request, question_id):
      question = get_object_or_404(Question, pk=question_id)
      return render(request, 'polls/results.html', {'question': question})



