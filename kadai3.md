課題３　閾値処理
閾値を4パターン設定し,閾値処理をした画像を示せ．．

clear; % 変数のオールクリア

ORG=imread('cola.png'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai3_1.png?raw=true)  
図１　白黒濃淡画像

IMG = ORG > 32;
imagesc(IMG);colormap(gray); colorbar;

輝度値を32に設定し、以上を白く(画素を1)、それ以下を黒く(画素を0)表示する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai3_2.png?raw=true)  
図2　閾値32の場合

IMG = ORG > 64; 
imagesc(IMG); colormap(gray); colorbar;

輝度値を64に設定する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai3_3.png?raw=true)  
図3　閾値64の場合

IMG = ORG > 96;
imagesc(IMG); colormap(gray); colorbar;

輝度値を96に設定する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai3_4.png?raw=true)  
図4　閾値96の場合

IMG = ORG > 128;
imagesc(IMG); colormap(gray); colorbar;

輝度値を128に設定する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai3_5.png?raw=true)  
図5　閾値128の場合

IMG = ORG > 192;
imagesc(IMG); colormap(gray); colorbar;

輝度値を192に設定する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai3_6.png?raw=true)  
図6　閾値192の場合

画像より、輝度値を上げていくにつれ、輝度値以上の部分は0で表示されるので画像全体が黒くなっていくことがわかる。