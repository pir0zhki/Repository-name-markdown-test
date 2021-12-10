# Repository-name-markdown-test
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Step4.ベースレイヤの切り替え|Lefletの基本|埼玉大学谷謙二研究室</title>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.3.0/dist/leaflet.css" />
  <script src="https://unpkg.com/leaflet@1.3.0/dist/leaflet.js"></script>
  <script>
    function init(){
      var map = L.map('mapcontainer',{zoomControl:false});
      map.setView([35.40, 136], 5);
      L.control.scale({maxWidth:200,position:'bottomright',imperial:false}).addTo(map);
      L.control.zoom({position:'bottomleft'}).addTo(map);
      //地理院地図の標準地図タイル
      var gsi =L.tileLayer('https://cyberjapandata.gsi.go.jp/xyz/std/{z}/{x}/{y}.png', 
        {attribution: "<a href='https://maps.gsi.go.jp/development/ichiran.html' target='_blank'>地理院タイル</a>"});
      //地理院地図の淡色地図タイル
      var gsipale = L.tileLayer('http://cyberjapandata.gsi.go.jp/xyz/pale/{z}/{x}/{y}.png',
        {attribution: "<a href='http://portal.cyberjapan.jp/help/termsofuse.html' target='_blank'>地理院タイル</a>"});
      //オープンストリートマップのタイル
      var osm = L.tileLayer('http://tile.openstreetmap.jp/{z}/{x}/{y}.png',
        {  attribution: "<a href='http://osm.org/copyright' target='_blank'>OpenStreetMap</a> contributors" });
      //baseMapsオブジェクトのプロパティに3つのタイルを設定
      var baseMaps = {
        "地理院地図" : gsi,
        "淡色地図" : gsipale,
        "オープンストリートマップ"  : osm
      };
      //layersコントロールにbaseMapsオブジェクトを設定して地図に追加
      //コントロール内にプロパティ名が表示される
      L.control.layers(baseMaps).addTo(map);
      gsi.addTo(map);
    }
  </script>   
</head>
<body onload="init()">
  <div id="mapcontainer" style="position:absolute;top:0;left:0;right:0;bottom:0;"></div>
</body>
</html>
