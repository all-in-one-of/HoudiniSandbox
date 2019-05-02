## HoudiniVEX_sample
VEXのイディオム的なの

---
### VEX  - EXPRESSION

- 値のセット

  ```C++
  @P += set(0.5,2,0);
  @Cd = set(0,1,0);
  @N = @N;
  
  @N = set(1,0,0);
  @v = @N;
  ```

- バウンディングボックスから色を取得

  ```C++
  @Cd = relbbox(0, @P);
  ```

- ベロシティにセットしてパーティクルで動きのコントロール

  ```C++
  @Cd = relbbox(0, @P);
  @v = @N*@Cd.g * ch("m");
  @v = set(5,0,0);
  ```

- ポイント番号と総ポイント数を使ったコントロール

  ```C++
  //@Cd = 0;
  //f@b = @ptnum;
  //@Cd.r = @b/@numpt;
  //@Cd.r = @ptnum/(@numpt*1.0);
  //@Cd.r = rand(@ptnum);
  
  @Cd = noise(@P/2 + @Time);
  f@b = chramp("m", @Cd.r);
  
  f@zscale = @b * rand(@ptnum);
  ```

- lerpを使ったモーフィング

  ```C++
  v@bb = relbbox(2, @P);
  @Cd = @bb;
  f@g = clamp(@Cd.g, 0, 1);
  @Cd.g = @g;
  //@P = lerp(@P, @opinput1_P, ch("m"));
  @P = lerp(@P, @opinput1_P, @g);
  ```

- 閾値でポイントをランダムに削除する

  ```C++
  if(rand(@ptnum) > ch('threshold')){
      removepoint(0, @ptnum);
  }
  ```

- 波のデフォーマー(Grid SOP)

  ```C++
  float d;
  float scale;
  float speed;
  float height;
  float falloff;
  
  d = length(@P);
  scale = ch('scale');
  speed = @Time * ch('speed');
  height = ch('height');
  falloff = fit(d, ch('start'), ch('end'), 1, 0);
  
  @P.y = sin(d * scale + speed);
  @P.y *= height;
  @P.y *= chramp('falloff', falloff);
  ```

- 










