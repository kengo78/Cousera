## データ拡張と画像拡張
データサイズを大きくする⇒モデルの性能を挙げれ鵜
これらをTensorflowで行う
画像generatorライブラリ
- keras Preprocessing layers
過学習を防ぎ、柔軟性を向上させる
拡張
画像の中での明確な特徴　⇒　畳み込み
回転を用いた拡張を使えば、違う角度でも明確な特徴をとらえることできる。
Image data preprocessing
```python
tf.keras.preprocessing.image_dataset_from_directory(
    directory,
    labels="inferred",
    label_mode="int",
    class_names=None,
    color_mode="rgb",
    batch_size=32,
    image_size=(256, 256),
    shuffle=True,
    seed=None,
    validation_split=None,
    subset=None,
    interpolation="bilinear",
    follow_links=False,
    crop_to_aspect_ratio=False,
    **kwargs
)
```
rescaleも画像拡張の1つ
ImageDataGeneratorを用いた画像拡張
```python
train_datagen = ImageDataGenerator(
    rescale = 1./255.
    rotation_range=40,#回転範囲
    width_shift_range =0.2,#画像をランダムに移動させる
    height_shift_range=0.2,
    shear_range=0.2,#画像をせん断する
    zoom_range=0.2,#相対比率でのzoom
    horizontal_flip=True,#左右反転
    fill_mode='nearest'),
)
```
