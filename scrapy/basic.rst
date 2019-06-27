Basic
=====

Create a Project 

.. code:: sh

  scrapy startproject tutorial


directory structure

.. code:: sh

  tutorial/
      scrapy.cfg            # deploy configuration file

      tutorial/             # project's Python module, you'll import your code from here
          __init__.py

          items.py          # project items definition file

          middlewares.py    # project middlewares file

          pipelines.py      # project pipelines file

          settings.py       # project settings file

          spiders/          # a directory where you'll later put your spiders
              __init__.py




Run a spider

.. code:: sh

  scrapy crawl quotes


Scrapy Shell

.. code:: sh

  scrapy shell 'http://quotes.toscrape.com/page/1/'






Output File
===========

command: 

.. code:: sh

  scrapy runspider quotes_spider.py -o quotes.json



utf-8 setting

``setting.py``

.. code:: sh

  FEED_EXPORT_ENCODING = 'utf-8'

