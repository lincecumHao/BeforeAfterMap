# BeforeAfterMap （Google Maps API V3)
JQ Before After for google maps

A simple example for using beforeAfter jq class.

#[DEMO](http://lincecumhao.github.io/BeforeAfterMap)

#Replace:
  (1)_before_.options.inertia = false; <br />
  (2)_before_._container<br />
  (3)_before_.on('dragend', _mapMove_).on('zoomend', _mapMove_);<br />
#To:
  (1)google.maps.event.addListener(_before_, 'idle', function() { _after_.panTo(_before_.getCenter());});<br />
  (2)_before_.getDiv()<br />
  (3)google.maps.event.addListener(_before_, 'idle', _mapMove_);<br />

Done :P

之前看到了一個網站 <a href="http://www.esri.com/services/disaster-response/hurricanes/hurricane-sandy-the-aftermap">Hurricane Sandy: The AfterMap</a>, 是用ArcGIS Server + Portal 做出來的，Googel 了一下發現 <a href="http://datatools.metrotrends.org/charts/metrodata/_Blog/Maps/BeforeAfter/index.cfm">這個API</a>, 但是只有支援兩種圖台Mapbox, Leaflet ，就是沒有Googel Maps，所以自己修改了一下給大家參考。
