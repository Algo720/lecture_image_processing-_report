課題９ メディアンフィルタと先鋭化
メディアンフィルターを適用し，ノイズ除去を体験せよ．


ORG = imread('cola.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai9_1.png?raw=true)  
図1　白黒濃淡画像

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

ここで意図的にノイズを付与する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai9_2.png?raw=true)  
図2　ノイズを付与した画像

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

ノイズのがる画像に対して平滑化フィルタでノイズを除去する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai9_3.png?raw=true)  
図3　平滑化フィルタ後の画像

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

同じくメディアンフィルタでノイズ除去。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai9_4.png?raw=true)  
図4　メディアンフィルタ後の画像

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

ここでは自身でフィルタを設計し適用している。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai9_5.png?raw=true)  
図5　設計フィルタ後の画像

平滑化フィルタでは全体的にノイズが薄まっているが、まだノイズが認識できてしまう。また、平滑化しているため、画像の輪郭が
かなりぼやけてしまっている。

メディアンフィルタではきれいにノイズも除去できていて輪郭も比較的きれいに残っている。

自身で設定したフィルタではノイズはきれいに除去できていて、輪郭もきれいに残っているが画像の色が全体的に灰色になってしまっているため、
ここからさらに画像の修正が必要に感じた。
