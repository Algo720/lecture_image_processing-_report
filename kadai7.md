課題7　ダイナミックレンジの拡大
画素のダイナミックレンジを０から２５５にせよ． 

ORG = imread('cola.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai7_1.png?raw=true)  
図1　白黒濃淡画像

imhist(ORG); % 濃度ヒストグラムを生成、表示

図1の濃度ヒストグラムを表示する。
![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai7_2.png?raw=true)  
図2　図1の濃度ヒストグラム


ORG = double(ORG);
mn = min(ORG(:)); % 濃度値の最小値を算出
mx = max(ORG(:)); % 濃度値の最大値を算出
ORG = (ORG-mn)/(mx-mn)*255;
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai7_3.png?raw=true)  
図3　ダイナミックレンジ変更後の画像

ORG = uint8(ORG); 
imhist(ORG); % 濃度ヒストグラムを生成、表示

![原画像](https://github.com/Algo720/lecture_image_processing-_report/blob/master/image/kadai7_4.png?raw=true)  
図4　図3の濃度ヒストグラム

ここでuint8とは画像を「8 ビット符号なし整数への変換」することである。8ビットとはつまり、0～255をあらわすことが出来る。
そのためこのuint8を使用すると整数で表したORGの中に255を超える値(または0を下回る値)が存在した場合、一番近い端店(0か255)
の値に変換するものである。
ここで使用されている理由はダイナミックレンジを0～255までに設定しているのでそれに画像を合わせるためだと思われる。

ダイナミックレンジ使用前後の画像を比較すると、白黒濃淡画像には変化がないように見られる。
しかし、濃度ヒストグラムでは輝度値60付近と輝度値190付近の画素が消えていることがわかった。