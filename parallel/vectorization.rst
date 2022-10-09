Vectorization
================


-fvectorize, -fno-vectorize
-----------------------------

Enables or disables the generation of Advanced SIMD (Neon®), M-profile Vector Extension (MVE), and Scalable Vector Extension (SVE) vector instructions directly from C or C++ code at optimization levels ``-O1`` and higher.



- At optimization level ``-O2`` and above, the default is ``-fvectorize``. Use ``-fno-vectorize`` to disable automatic vectorization.

|

.. code:: c

  void test1(float* a, float* b, float* c, int N) {
    __builtin_assume(N == 1024);

    for (int i=0; i<I; i++) {
      for (int j=0; j<N; j++) {
        c[j] = a[j] + b[j];
      }
    }
  }


- `Compiler Explorer <https://godbolt.org/>`_


|

Reference
-----------

- `Arm Compiler for Embedded Reference Guide <https://developer.arm.com/documentation/101754/0618/armclang-Reference/armclang-Command-line-Options/-fvectorize---fno-vectorize>`_


