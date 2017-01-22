課題４　画像のヒストグラム
画素の濃度ヒストグラムを生成せよ．

clear; % 変数のオールクリア

ORG=imread('cola.png'); % 原画像の入力
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;

まずは濃度ヒストグラムを表示するために画像を白黒濃淡画像にする。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai4_1.png?raw=true)  
図1　白黒濃淡画像

imhist(ORG);

次に濃度ヒストグラムを表示する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai4_2.png?raw=true)  
図2　濃度ヒストグラム

濃度ヒストグラムと画像を見比べてみると画像が全体的に暗いもののため、濃度ヒストグラムでも輝度値が低い値の部分が
かなり高い結果となっている。
