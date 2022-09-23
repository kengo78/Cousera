# cousera
## python環境作成
pyenvとpipenvを組み合わせて作る。
### pyenv　インストール

```
$ brew update
$ brew install pyenv
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
```
その後、
```
$ source ~/.zshrc
```
で変更を適用する。

```
$ pyenv install --list
```
上記コマンドでインストール可能なversionがみれる。
その後、使いたいversionをインストールする
```
$ pyenv install 3.9.5
```

#### pipenv install
```
$ brew update 
$ brew install pipenv
```

環境の作成
```
pipenv --python 3.9.5
```
実行すると、以下のようにPipfileが作成される
```
[[source]]
url = "https://pypi.org/simple"
verify_ssl = true
name = "pypi"

[packages]

[dev-packages]

[requires]
python_version = "3.9"
```

#### ライブラリインストール
```
$ pipenv install numpy
```
そうすると、Pipfile.lockが同じディレクトリに作成される

#### 仮想環境への入り方と出る方法
```
$ pipenv shell
$ exit
````

