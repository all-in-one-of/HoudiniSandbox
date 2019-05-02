## Houdini VEX
よく使うVEXまとめ

---
### VEX  - EXPRESSION

- **`fit()`**
  2つの値を受け取り、それを他の2つの値(通常は0-1)にフィットします。例えば、@uを-5,20の範囲から0-1の範囲にリマップします.
  **`foo = fit(@u, -5, 20, 0, 1);`**

- **`rand()`**
  0以上1未満の乱数を生成します。通常では、ポイント毎に異なる乱数が得られるように引数にポイントIDを渡します.
  **`foo = rand(@ptnum);`**

- **`sin()`**
  単位はラジアン

- **`cos()`**
  単位はラジアン

- **`radians()`**
  数値を度からラジアンに変換します
  **`foo = radians(90);`**

- **`length()`**
  ベクトルの長さを測定します。例えば、原点からポイントまでの距離を測定します
  **`dist = length(@P);`**

- **`distance()`**
  2つのポイント間の距離を測定します
  **`dist = distance(@P, v@mypoint);`**

- **`cos()`**

- **$F**：フレーム番号を表す変数

- **ch()**
  指定したパラメーターを参照
  http://www.sidefx.com/docs/houdini/vex/functions/ch.html

  ```C++
  float ch(string channel)
  // - string: 参照先のパスを指定
  ```

- **`opinputpath()`**
  指定したノードに入力されたノードのパスを取得

- **`normalize()`**

- **`radians()`**

- **`set()`**

- **`normalize()`**

- **`findattribval()`**

- **`addprim()`**

- **`setprimgroup()`**

- **`point()`**

- **`addpoint()`**

- **`distance()`**

- **`setpointattrib()`**

- **`addvertex()`**

- **`itoa()`**
  整数を文字列に変換

- **`split()`**
  文字列をトークンに分割
  <https://www.sidefx.com/docs/houdini/vex/functions/split.html>

- **`splitpath()`**
  ファイルパスをディレクトリ部分と名前部分に分ける
  https://www.sidefx.com/docs/houdini/vex/functions/splitpath.html

- **`addvertex()`**

- **`addvertex()`**

- **`addvertex()`**

- **`addvertex()`**

- **`addvertex()`**

- **`addvertex()`**

- 










