=========================
	Multimedia	
=========================

+ Spatial Filtering 空間濾波
	https://www.slideshare.net/YKLee3434/spatial-filtering-41713087

+ Gaussian Blur Filter
	sigma — Standard deviation of the Gaussian distribution


========================
	中英對照
========================

standard deviation 標準差


===============================
	Median Filter
===============================

Median Filter 中值濾波器

median 中位數

假設 convolution mask 3x3 : 
	
	





=================================
	Gaussian Filter		
=================================

http://www.ruanyifeng.com/blog/2012/11/gaussian_blur.html

使用 Gaussion function , 帶入參數 x, y, sigma 得到 convolution mask

假設 convolution mask 是 3x3 , sigma = 1.5 :

	x, y 分別帶入:

	(-1, 1)  ( 0, 1)   ( 1, 1)

	(-1, 0)  ( 0, 0)   ( 1, 0)

	(-1,-1)  ( 0,-1)   ( 1,-1)


	得到一組 3x3 的 matrix A
	將 A 取加權平均(a/a+b+c) 得到 convolution mask

	










