# pico-blink-easy
Pico example which automatically download the SDK. 

# Details
このプログラムはRaspberryPi Picoのサンプルです。

ビルド中にpico-sdkをダウンロードするため、あらかじめpico-sdkを
設定する必要がありません。

Ubuntu 22.04でテスト済みです。

# Setup environment
[rpi_pico_env_setup](https://github.com/suikan4github/rpi_pico_env_setup) のスクリプトを使って環境設定を行ってください。

このスクリプトはビルドに必要なツール類をインストールします。

# How to build in Linux Command Line
コマンドラインから実行する場合は、以下のコマンドを実行してください。
```
mkdir build
cd build
cmake ..
make
```
この間、Pico-sdkのダウンロードも行うため、少し時間がかかります。

ビルド結果はbuildサブディレクトリに出力されます。

# How to build in VS Code
## Configure VS Code
VS Codeの拡張機能に[C/C++ Extention Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools-extension-pack)をインストールしてください。

この拡張機能はC++言語のシンタックス・ハイライティングやIntelli-senseによる入力保管を行う他、CMake拡張機能も含んでいます。
## Build
コマンドパレット(ctrl-shift-P)から、
```
Cmake : Configure
```
を実行してください。CMake拡張機能が自動的にコンパイラを探し出してプロジェクトのコンフィギュレーションを行います。この間、Pico-sdkのダウンロードも行うため、少し時間がかかります。

念の為、ステータスバーでコンパイラがGCC XX.X.X arm-none-eabiで有ることを確認してください。下の図の例ではGCC 10.3.1 arm-none-eabiになっています。

![](image/Screenshot_startus_bar.png)

arm-none-eabiではない場合には、ステータスバーの当該位置をクリックすることで、メニューバーからプルダウンが現れますので適切なコンパイラを選んでください。

![](image/Screenshot_compiler_pull_down.png)

コンパイラを選び終わったら、ステータスバーのBuildをクリックすることでビルドすることができます。

ビルド結果はbuildサブディレクトリに出力されます。