課題６　画像の二値化
下記のプログラムを参考にして画像を二値化せよ．

clear; % 変数のオールクリア

ORG=imread('cola.png'); % 原画像の入力
ORG = rgb2gray(ORG);
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai6_1.png?raw=true)  
図1　白黒濃淡画像

IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

輝度値を128に設定し、2値化する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai6_2.png?raw=true)  
図2　輝度値128での2値化

IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

ディザ法での2値化
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai6_3.png?raw=true)  
図3　ディザ法でも2値か

輝度値128の2値化の場合画像が全体的に暗く、課題5の判別分析法と比べると画像がわかり辛いものとなった。

ディザ法では全体的な輪郭はつかめるが、ノイズのようなドットが多く表示されてしまっているため、わかり辛い部分がある。
