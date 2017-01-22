課題８ ラベリング
二値化された画像の連結成分にラベルをつけよ．

ORG = imread('cola.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai8_1.png?raw=true)  
図1　白黒濃淡画像

IMG = ORG > 128; % 閾値128で二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai8_2.png?raw=true)  
図2　輝度値128で2値化した画像

IMG = bwlabeln(IMG);
imagesc(IMG); colormap(jet); colorbar; % 画像の表示

bwlabelnを使用し画像内の連結要素をラベル付けし、その後colormap(jet)でサーモグラフィのような青色から赤色までの
カラーで画像を表示する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai8_3.png?raw=true)  
図3　ラベリング後の画像

ラベリング後の画像を見ると画像が全体的に暗いため、画像のほとんどが青く染まっている。

