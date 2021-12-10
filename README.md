# Repository-name-markdown-test
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Step1.Leafletで地理院地図を表示する最も基本的なコード|Lefletの基本|埼玉大学谷謙二研究室</title>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.3.0/dist/leaflet.css" />
  <script src="https://unpkg.com/leaflet@1.3.0/dist/leaflet.js"></script>
  <script>
    function init() {
      //地図を表示するdiv要素のidを設定
      var map = L.map('mapcontainer');
      //地図の中心とズームレベルを指定
      //南緯西経はマイナス
      //OpenStreetMapから緯度経度を取得して張り付けたりする
      map.setView([-15, -48], 5);
      //表示するタイルレイヤのURLとAttributionコントロールの記述を設定して、地図に追加する
      L.tileLayer('https://cyberjapandata.gsi.go.jp/xyz/std/{z}/{x}/{y}.png', {
          attribution: "<a href='https://maps.gsi.go.jp/development/ichiran.html' target='_blank'>地理院タイル</a>"
      }).addTo(map);
    }
  </script>
</head>
<body onload="init()">
  <div id="mapcontainer" style="width:600px;height:600px"></div>
</body>
</html>
