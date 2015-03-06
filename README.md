# BeforeAfterMap
JQ Before After for google maps

A simple example for using beforeAfter jq class.

Replace:
  _before_.options.inertia = false;
To:
  google.maps.event.addListener(_before_, 'idle', function() { _after_.panTo(_before_.getCenter());});

Replace all:
  _before_._container
To:
  _before_.getDiv()
  
Replace:
  _before_.on('dragend', _mapMove_).on('zoomend', _mapMove_);
To
  google.maps.event.addListener(_before_, 'idle', _mapMove_);
  
Done :P
