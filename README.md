方案 D：GML 分區動態載入版

GitHub Pages 上傳方式：
1. 將 index.html 上傳到你的 GitHub Pages 網站根目錄，或改成你原本使用的 HTML 檔名。
2. 將 pipe_tiles 整個資料夾一併上傳，且必須與 index.html 同一層。

結構範例：
  /index.html
  /pipe_tiles/manifest.json
  /pipe_tiles/tile_13411_2593.geojson
  /pipe_tiles/...

這版不再讓手機直接載入 PIPE.gml，而是只載入目前畫面附近的 geojson 小分區。
若要重新用新的 PIPE.gml 產生分區，請在電腦執行：
  pip install pyproj shapely
  python convert_gml_to_pipe_tiles.py PIPE.gml pipe_tiles --tile-size 1000 --simplify 0.2

參數建議：
  --tile-size 1000  每格 1000 公尺，穩定、請求數較少
  --tile-size 500   每格 500 公尺，更省單次載入量，但請求數較多
  --simplify 0.2    線段簡化 0.2 公尺，適合 1:1000 附近顯示
  --simplify 0      不簡化，精度最高但檔案較大
