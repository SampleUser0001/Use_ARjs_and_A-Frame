# Use_ARjs_and_A-Frame
AR.jsとA-Frameを使ってみる

## index.html

```
<!doctype HTML>
<html>
<!-- A-Frame ライブラリの読み込み -->
<script src="https://aframe.io/releases/0.8.2/aframe.min.js"></script>
<!-- AR.js ライブラリの読み込み -->
<script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.5.0/aframe/build/aframe-ar.js"></script>
<body style='margin:0px; overflow:hidden;'>
<!-- こっからA-Frame -->
<a-scene embedded arjs="debugUIEnabled:false;trackingMethod:best;" vr-mode-ui="enabled: false">
    <!-- オブジェクトファイルとマテリアルファイルを読み込む -->
    <a-assets>
        <a-asset-item id="santa-obj" src="model_obj/santa/santa.obj"></a-asset-item>
        <a-asset-item id="santa-mtl" src="model_obj/santa/santa.mtl"></a-asset-item>
    </a-assets>
    <!-- こっからARの世界。マーカー上になにを展開するかを書く -->
    <a-marker preset="hiro">
        <a-obj-model id="santa" src="#santa-obj" mtl="#santa-mtl" position="0 0 0" scale="0.5 0.5 0.5" rotation="0 0 0"></a-obj-model>
        <a-text value="Hello YouTube！!！" position="0 1.3 0" align="center"></a-text>
    </a-marker>
    <!-- arなのでこんな感じでカメラが必要らしい。 -->
    <a-entity camera></a-entity>
</a-scene>
<!-- ここまででA-Frameおわり -->
</body>
</html>
```

- a-sceneタグ
  - A-Frameタグを使用する宣言。  
- a-asserts
  - 資材ロードするためのタグ。
  - a-asset-item
    - ロードする資材を指定する。
- a-marker
  - presetで指定したマーカーがカメラに写ったときの挙動
    - 「hiro」は「Hiro」って書いてあるマーカー。
  - 子要素に表示させたいものを記載する。

## 参考

- [Qiita : 【AR.js入門】簡単にWebARで遊んでみた【A-Frame使うよ】](https://qiita.com/sakaryu/items/769a2a538baf7e4ee1c7)
  - オリジナルはこれ。

- [A-Frame](https://aframe.io/docs/1.0.0/introduction/)
  - [a-scene](https://aframe.io/docs/1.0.0/core/scene.html#sidebar)
  - [a-asserts](https://aframe.io/docs/1.0.0/core/asset-management-system.html)
  - a-marker
    - 見つからない…
