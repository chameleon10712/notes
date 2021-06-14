Tensor Processing Unit (TPU)
==================================

Tensor Processing Unit (TPU) is an AI accelerator application-specific integrated circuit (ASIC)
developed by Google specifically for neural network machine learning,
particularly using Google's own TensorFlow software. 
Google began using TPUs internally in 2015, 
and in 2018 made them available for third party use, 
both as part of its cloud infrastructure and by offering a smaller version of the chip for sale.
`[wiki] <https://en.wikipedia.org/wiki/Tensor_Processing_Unit>`_

|

Prediction with neural networks
------------------------------------

.. image:: https://storage.googleapis.com/gweb-cloudblog-publish/images/tpu-9jsw7.max-700x700.PNG


|


TPU Block Diagram
-----------------------


.. image:: https://storage.googleapis.com/gweb-cloudblog-publish/images/tpu-15dly1.max-500x500.PNG


|

|

From TensorFlow to TPU: the software stack

.. image:: https://storage.googleapis.com/gweb-cloudblog-publish/images/tpu-2x0vv.max-600x600.PNG



|

The heart of the TPU: A systolic array
-----------------------------------------



CPUs and GPUs often spend energy to access multiple registers per operation. A systolic array chains multiple ALUs together, reusing the result of reading a single register.


.. image:: https://storage.googleapis.com/gweb-cloudblog-publish/images/tpu-17u39j.max-500x500.PNG




- `[Google Cloud] An in-depth look at Google’s first Tensor Processing Unit (TPU) <https://cloud.google.com/blog/products/ai-machine-learning/an-in-depth-look-at-googles-first-tensor-processing-unit-tpu>`_




