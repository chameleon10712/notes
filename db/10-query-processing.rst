Query Processing
===================


- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|

- `[Video] <https://www.youtube.com/watch?v=vmI72W-vgYI&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=10>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/10-queryprocessing.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/10-queryprocessing.pdf>`_
- Readings: Chapter 12.1-12.3, 12.7




|

Term
------

- predicate

  - A predicate is the formal name for when an expression is used to evaluate a TRUE or FALSE condition (or sometimes UNKNOWN if a TRUE/FALSE value can't be determined)
  - ex. 
  
    - ``JOIN Country ON Customer.countryCode = Country.countryCode``
    - ``WHERE Country.nickName IN ('USA', 'UK', 'Japan')``
    
  - `What is a predicate in SQL? <https://www.quora.com/What-is-a-predicate-in-SQL>`_




