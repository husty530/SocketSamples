# SocketSamples

## 異言語間を行き来するためのTCPソケット
複数のプログラミング言語でやりとりする方法はDLLIMPORTやメモリ共有などあるわけですが、
結局のところ全部バイナリレベルで繋ぐことができればすっきりするのではないかと考え、このような雛型を作成してみました。
サンプル内のやり方では文字列と数値の受け渡ししかしていませんが、配列や画像もエンコード、デコードをかければ同じように扱うことができます。  
気を付けるべきはサーバーとクライアントが息ぴったりでないと謎のスタックを起こすことです。  
例えばサンプルではすべて文字列の終端に改行コードを入れていますが、この統一性を失うと突然メッセージが来ない、なんてことになります。  
自分でやるときはそのへんの設定もオリジナルでやることになると思います。どうかお気を付けください。  
  
# Contents
今のところC++, C#, JavaScript(node.js), Pythonに対応しています。  
ということは、もうこの4つはちょっと手を焼けば互いの情報をやりとりできるということです。  
デバッグはVisualStudioの中で完結するようにまとめました。ソリューションエクスプローラがなかなかカオス。。。  
![sockets.png](/sockets.png)  
  
# Preparation
* Windows10
* VisualStudio2019  
必要に応じてインストーラからコンポーネントを入れてください。  
* C++ -- C++デスクトップ開発
* C# -- .NETデスクトップ開発
* JavaScript -- node.js開発、別途node.jsをインストール
* Python -- Python開発、別途Pythonをインストール  
  
# How to Use
どのプロジェクトもVisualStudioでデバッグを実行できますし、
C++とC#はデスクトップアプリとしてビルド、JavaScriptとPythonは普通のスクリプトファイルとして実行できます。  
内容物はあくまで雛型なので、中身を書き換えてご利用ください。  
  
クライアントが送るメッセージは数値をバイナリに変換してるのですが、C++だけsizeof(sendmsg)がバカになっていて
なぜがstrlen(sendmsg)ならちゃんとしてたという謎が残っております。怖い。もうやりたくない。
