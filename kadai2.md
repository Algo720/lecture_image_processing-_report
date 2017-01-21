課題２　階調数と疑似輪郭
２階調，４階調，８階調の画像を生成せよ．

まずは、白黒画像を作成する。

clear; % 変数のオールクリア

ORG=imread('cola.png'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai2_1.png?raw=true)  
図1　白黒濃淡画像

% ２階調画像の生成
IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;

輝度値を256の2分の1である128とし、これ以上の濃度を黒く、これ以下の濃度を白くし、2階調画像を作成する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai2_2.png?raw=true)  
図2　2階調画像

% ４階調画像の生成
IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;

輝度値を256の4分の1である64を基準として、4つの濃度に分ける。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai2_3.png?raw=true)  
図3　4階調画像


%　8階調画像の生成
IMG0 = ORG > 32;
IMG1 = ORG > 64;
IMG2 = ORG > 98;
IMG3 = ORG > 128;
IMG4 = ORG > 160;
IMG5 = ORG > 192;
IMG6 = ORG > 224;
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;

輝度値を256の8分の1である32を基準として、8つの濃度に分ける。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai2_4.png?raw=true)  
図4 ８階調画像

これより、２階調画像より４階調画像、さらに８階調画像のほうが、画像が鮮明に表現されている。
よって、この階調が増えれば増えるほど画像が鮮明になっていくことがわかった。
