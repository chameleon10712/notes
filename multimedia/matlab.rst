======================
 	Matlab
======================

uint8 : 8-bit unsigned integer
im2double : Convert image to double precision

standard deviation 標準差

 Just write 
 >> edit interp2 
 in the command window and you can check out how they implemented it.

imread ::

	I = imread('/Users/oceane/Documents/MATLAB/HW1_data/lalaland.png');	

imfinfo ::
	
	info1 = imfinfo('/Users/oceane/Documents/MATLAB/HW1_data/lalaland.png');

*** stackoverflow : rayryeng -> 這個人超強！！！
	http://stackoverflow.com/users/3250829/rayryeng

關鍵字 : 
	知乎, 簡體專有名詞


======================
	PSNR		
======================

hydai github
	https://github.com/hydai/Multimedia/blob/master/HW1/MyPSNR.m



============================================
   divide an image into blocks in MATLAB
============================================

http://stackoverflow.com/questions/1637000/how-to-divide-an-image-into-blocks-in-matlab



======================
	DCT
======================
關鍵字 : 离散余弦变换

http://www.cnblogs.com/lzhen/p/3947600.html
http://blog.csdn.net/zhe123zhe123zhe123/article/details/46385591

mask :
http://stackoverflow.com/questions/2839696/quantize-dct-cofficents-in-matlab


測試 ::
	X=round(rand(8)*100);
	X=double(X);
	Y=blkproc(X,[8 8],'dct21');
	X1=blkproc(Y,[8 8],'dct22');
	subplot(1,3,1);
	imshow(uint8(X));
	subplot(1,3,2);
	imshow(uint8(Y));
	subplot(1,3,3);
	imshow(uint8(X1));

轉成灰階 ::

	I = rgb2gray(RGB);

灰階dct 測試 :: 

	I=imread('/Users/oceane/Documents/MATLAB/HW1_data/lalaland.png');
	I=rgb2gray(I);
	X=double(I);
	Y=blkproc(X,[8 8],'dct21');
	mask = [
	     1   1   1   1   0   0   0   0
	     1   1   1   1   0   0   0   0
	     1   1   1   1   0   0   0   0
	     1   1   1   1   0   0   0   0
	     0   0   0   0   0   0   0   0
	     0   0   0   0   0   0   0   0
	     0   0   0   0   0   0   0   0
	     0   0   0   0   0   0   0   0];
	Y1 = blockproc(Y,[8 8],@(block_struct) mask .* block_struct.data);
	X1=blkproc(Y1,[8 8],'dct22');
	imshow(uint8(X));
	figure
	imshow(uint8(X1));



RGB -> YIQ  使用Matlab 內建function : rgb2ntsc, ntsc2rgb ::
	
	I=imread('/Users/oceane/Documents/MATLAB/HW1_data/lalaland.png');
	YIQ=rgb2ntsc(I);
	%{
	imshow(uint8(YIQ))
	imshow(YIQ(:,:,1));
	imshow(YIQ(:,:,2));
	imshow(YIQ(:,:,3));
	%}
	
	y=YIQ(:,:,1);
	i=YIQ(:,:,2);
	q=YIQ(:,:,3);
	
	yY=blkproc(y,[8 8],'dct21');
	yX1=blkproc(yY,[8 8],'dct22');
	
	iY=blkproc(i,[8 8],'dct21');
	iX1=blkproc(iY,[8 8],'dct22');
	
	qY=blkproc(q,[8 8],'dct21');
	qX1=blkproc(qY,[8 8],'dct22');
	
	newYIQ=cat(3,y,i,q);
	
	RGB2 = ntsc2rgb(newYIQ);
	imshow(RGB2);
		



拆成RGB 三個 value ::

	I=imread('/Users/oceane/Documents/MATLAB/HW1_data/lalaland.png');
	r=I(:,:,1);
	g=I(:,:,2);
	b=I(:,:,3);
	RGB=cat(3,r,g,b);
	imshow(RGB);



lalaland.png 拆成 RGB 三個 value 後使用Matlab內建 dct2 , idct2 ::

	I=imread('/Users/oceane/Documents/MATLAB/HW1_data/lalaland.png');
	r=I(:,:,1);
	g=I(:,:,2);
	b=I(:,:,3);
	R=double(r);
	G=double(g);
	B=double(b);
	RY=blkproc(R,[8 8],'dct2');
	R1=blkproc(RY,[8 8],'idct2');
	GY=blkproc(G,[8 8],'dct2');
	G1=blkproc(GY,[8 8],'idct2');
	BY=blkproc(B,[8 8],'dct2');
	B1=blkproc(BY,[8 8],'idct2');
	RGB=cat(3,R1,G1,B1);
	imshow(uint8(RGB));


使用自定義function dct21 , dct22 ::

        I=imread('/Users/oceane/Documents/MATLAB/HW1_data/lalaland.png');
        r=I(:,:,1);
        g=I(:,:,2);
        b=I(:,:,3);
        R=double(r);
        G=double(g);
        B=double(b);
        RY=blkproc(R,[8 8],'dct21');
        R1=blkproc(RY,[8 8],'dct22');
        GY=blkproc(G,[8 8],'dct21');
        G1=blkproc(GY,[8 8],'dct22');
        BY=blkproc(B,[8 8],'dct21');
        B1=blkproc(BY,[8 8],'dct22');
        RGB=cat(3,R1,G1,B1);
        imshow(uint8(RGB));

dct21 ::

	function Y = dct21(X)
	[m,n] = size(X);
	FM = zeros(m,m);   
	FN = zeros(n,n);
	for i = 0:m-1
	    for j = 0:m-1
		if i == 0
		    FM(i+1,j+1) = sqrt(1/m)*cos(((2*j+1)*i*pi)/(2*m));
		else
		    FM(i+1,j+1) = sqrt(2/m)*cos(((2*j+1)*i*pi)/(2*m));
		end
	    end
	end
	for i = 0:n-1
	    for j = 0:n-1
		if i == 0
		    FN(i+1,j+1) = sqrt(1/n)*cos(((2*j+1)*i*pi)/(2*n));
		else
		    FN(i+1,j+1) = sqrt(2/n)*cos(((2*j+1)*i*pi)/(2*n));
		end
	    end
	end
	X = double(X);      %注意变换后的矩阵数据类型为double
	Y = FM*X*FN';      
	end


dct22 ::

	function Y = dct22(X)
	[m,n] = size(X);
	FM = zeros(m,m);   
	FN = zeros(n,n);
	for i = 0:m-1
	    for j = 0:m-1
		if i == 0
		    FM(i+1,j+1) = sqrt(1/m)*cos(((2*j+1)*i*pi)/(2*m));
		else
		    FM(i+1,j+1) = sqrt(2/m)*cos(((2*j+1)*i*pi)/(2*m));
		end
	    end
	end
	for i = 0:n-1
	    for j = 0:n-1
		if i == 0
		    FN(i+1,j+1) = sqrt(1/n)*cos(((2*j+1)*i*pi)/(2*n));
		else
		    FN(i+1,j+1) = sqrt(2/n)*cos(((2*j+1)*i*pi)/(2*n));
		end
	    end
	end
	X = double(X);      %注意变换后的矩阵数据类型为double
	Y = FM'*X*FN;       %实现DCT逆变换仅仅将本行换为Y = FM'*X*FN即可
	end









==================================
	Median Filter		
==================================


stackoverflow
	http://stackoverflow.com/questions/27535535/matlab-median-filter-code

N = 3;
im = imread('/Users/oceane/Documents/MATLAB/HW1_data/thinker_gray_noised.jpg');

im_pad = padarray(im, [floor(N/2) floor(N/2)]);
im_col = im2col(im_pad, [N N], 'sliding');
sorted_cols = sort(im_col, 1, 'ascend');
med_vector = sorted_cols(floor(N*N/2) + 1, :);
out = col2im(med_vector, [N N], size(im_pad), 'sliding');
imshow(out)


解釋:

padarray : 為處理影像四周鄰邊的點，影像資料必先向外填充 (padding) 
im2col   : Rearrange image blocks into columns 


==================================
	Gaussian Filter		
==================================

stackoverflow  
	http://stackoverflow.com/questions/27499057/how-do-i-create-and-apply-a-gaussian-filter-in-matlab-without-using-fspecial-im


N=3;  %// Define size of Gaussian mask
sigma=0.3; %// Define sigma here

%// Generate Gaussian mask
ind = -floor(N/2) : floor(N/2);
[X Y] = meshgrid(ind, ind);
h = exp(-(X.^2 + Y.^2) / (2*sigma*sigma));
h = h / sum(h(:));

%// Convert filter into a column vector
h = h(:);


%// Filter our image
I = imread('/Users/oceane/Documents/MATLAB/HW1_data/thinker_gray_noised.jpg');
I = im2double(I);
I_pad = padarray(I, [floor(N/2) floor(N/2)]);
C = im2col(I_pad, [N N], 'sliding');
C_filter = sum(bsxfun(@times, C, h), 1);
out = col2im(C_filter, [N N], size(I_pad), 'sliding');


imshow(out)


==========================================
	bilinear interpolation
==========================================

stackoverflow
	http://stackoverflow.com/questions/26142288/resize-an-image-with-bilinear-interpolation-without-imresize/26143655#26143655



===================================================
	nearest neighbor interpolation		
===================================================

stackoverflow
	http://stackoverflow.com/questions/25674691/resize-image-without-imresize-matlab



%# Initializations:

scale = [4 4];              %# The resolution scale factors: [rows columns]
oldSize = size(inputImage);                   %# Get the size of your image
newSize = max(floor(scale.*oldSize(1:2)),1);  %# Compute the new image size

%# Compute an upsampled set of indices:

rowIndex = min(round(((1:newSize(1))-0.5)./scale(1)+0.5),oldSize(1));
colIndex = min(round(((1:newSize(2))-0.5)./scale(2)+0.5),oldSize(2));

%# Index old image to get new image:

outputImage = inputImage(rowIndex,colIndex,:);

















