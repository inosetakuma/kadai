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

<img width="364" alt="dog2" src="https://user-images.githubusercontent.com/30037928/67668066-8f965600-f9b2-11e9-8663-bf6fb0e0b47a.png">
図2  1/2サンプリング

同様に原画像を1/4サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．すなわち，
IMG = imresize(ORG,0.5); % 画像の縮小
IMG2 = imresize(IMG,2,'box'); % 画像の拡大
とする．1/4サンプリングの結果を図３に示す．

<img width="365" alt="dog4" src="https://user-images.githubusercontent.com/30037928/67668211-d3895b00-f9b2-11e9-8ad6-ed88245e42b0.png">
図3 1/4サンプリング

1/8から1/32サンプリングは，
IMG = imresize(ORG,0.5); % 画像の縮小
IMG2 = imresize(IMG,2,'box'); % 画像の拡大
を繰り返す．サンプリングの結果を図４～６に示す．

<img width="365" alt="dog4" src="https://user-images.githubusercontent.com/30037928/67668605-9bcee300-f9b3-11e9-8b6f-b6cf2d00d558.png">
図4 1/8サンプリング

<img width="362" alt="dog5" src="https://user-images.githubusercontent.com/30037928/67668623-a5584b00-f9b3-11e9-9c32-3b3677f7b663.png">
図5 1/16サンプリング

<img width="364" alt="dog6" src="https://user-images.githubusercontent.com/30037928/67668633-ac7f5900-f9b3-11e9-9a5f-92a04d533b67.png">
図6 1/32サンプリング

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生することがわかる。
