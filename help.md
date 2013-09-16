## Count the number of crimes around an influence radius applied to each police station

UPDATE police_stations AS p SET n_of_closest_crimes = (SELECT count(cartodb_id) FROM crimes_2001_to_present_csv as c WHERE c.the_geom && ST_Buffer(p.the_geom,0.01))

## Find the police icon on the maki collection
http://www.mapbox.com/maki/src/police-24.svg