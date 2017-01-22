課題10 画像のエッジ抽出 
次のプログラムを参考にして，エッジ抽出を体験せよ．

ORG = imread('cola.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); %カラーからグレイへの変換
imagesc(ORG); colormap('gray'); colorbar;% 画像表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai10_1.png?raw=true)  
図1　白黒濃淡画像

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

プレウィット法を用いて画像からエッジを抽出する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai10_2.png?raw=true)  
図2　プレウィット法でのエッジ抽出

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

ソベル法を用いて画像からエッジを抽出する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai10_3.png?raw=true)  
図3　ソベル法でのエッジ抽出

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

キャニー法を用いて画像からエッジを抽出する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai10_4.png?raw=true)  
図4　キャニー法でのエッジ抽出

画像を比較すると、プレウィット法とソベル法ではあまり違いが見られなかった。
キャニー法ではほかのものと比較するときれいに輪郭が取れているように見えた。

これはキャニー法では物体の外側の輪郭だけでなく、内側の輪郭もとっているためきれいに見えているのだと考えられる。
