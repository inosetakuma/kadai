# kadai

標準画像「dog」を原画像をとする。

ORG=imread('Lenna.png'); % 原画像の入力
imagesc(ORG); axis image; % 画像の表示

によって、原画像を読み込み、表示した結果を図1に示す。

<img width="372" alt="dog" src="https://user-images.githubusercontent.com/30037928/67667252-c0758b80-f9b0-11e9-9511-e86483478fa1.png">
図1 原画像

原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．なお，拡大する際には，単純補間するために「box」オプションを設定する．

IMG = imresize(ORG,0.5); % 画像の縮小
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

1/2サンプリングの結果を図２に示す．

