# weewx-json
Extension for Prometheus Metrics endpoint from weewx

Based on [teeks99/weewx-json](https://github.com/teeks99/weewx-json)

This is most of the same data that can be found in the default "Seasons" report's `rss.xml` output, but formatted in
the prometheus metrics format for easier consumption by clients.


## Installing

Download the latest release from the [github releases](https://github.com/Cosmospacedog/weewx-metrics/releases) page

Run `wee_extension --install=weewx-metrics_X.X.tar.gz`

This will automatically add a `[[MetricsReport]]` to your weewx.conf file that will include the `metrics` file in your 
`HTML_ROOT`. 

## Uninstalling

Run `wee_extension --uninstall=weewx-metrics`

## Example Output

```conf
# =========================================
# Station metadata
# =========================================

# HELP weewx_station_info Static station metadata
# TYPE weewx_station_info gauge
weewx_station_info{location="WeeWX station",latitude="0.0",longitude="0.0",altitude_m="0.0",link=""} 1


# =========================================
# Generation metadata
# =========================================

# HELP weewx_generation_info WeeWX generator and generation time
# TYPE weewx_generation_info gauge
weewx_generation_info{generator="weewx 5.1.0",time="2026-01-05T11:35:00+0000"} 1


# =========================================
# Current conditions (gauges)
# =========================================

# HELP weewx_temperature Current outdoor temperature
# TYPE weewx_temperature gauge
weewx_temperature{units="°C"} 0.37547629147868217

# HELP weewx_dewpoint Current dewpoint
# TYPE weewx_dewpoint gauge
weewx_dewpoint{units="°C"} -2.666164243683956

# HELP weewx_humidity Current outdoor humidity
# TYPE weewx_humidity gauge
weewx_humidity{units="%"} 79.999999349267

# HELP weewx_heat_index Current heat index
# TYPE weewx_heat_index gauge
weewx_heat_index{units="°C"} 0.37547629147868217

# HELP weewx_barometer Current barometric pressure
# TYPE weewx_barometer gauge
weewx_barometer{units="mbar"} 1053.1667166573945

# HELP weewx_wind_speed Current wind speed
# TYPE weewx_wind_speed gauge
weewx_wind_speed{units="knots"} 9.424525400003968e-08

# HELP weewx_wind_gust Current wind gust
# TYPE weewx_wind_gust gauge
weewx_wind_gust{units="knots"} 2.63886710273944e-07

# HELP weewx_wind_direction Current wind direction
# TYPE weewx_wind_direction gauge
weewx_wind_direction{units="°"} 359.99999312082247

# HELP weewx_wind_chill Current wind chill
# TYPE weewx_wind_chill gauge
weewx_wind_chill{units="°C"} 0.37547629147868217

# HELP weewx_rain_rate Current rain rate
# TYPE weewx_rain_rate gauge
weewx_rain_rate{units="cm/h"} 0.0

# HELP weewx_inside_temperature Current indoor temperature
# TYPE weewx_inside_temperature gauge
weewx_inside_temperature{units="°C"} 17.22222246323444

# HELP weewx_inside_humidity Current indoor humidity
# TYPE weewx_inside_humidity gauge
weewx_inside_humidity{units="%"} 29.999999132356002


# =========================================
# Aggregate helpers
# period = day | week | month | year
# =========================================

# ---------- Temperature ----------

# HELP weewx_temperature_max Maximum temperature
# TYPE weewx_temperature_max gauge
weewx_temperature_max{period="day",units="°C"} 0.37699053901248425
weewx_temperature_max{period="week",units="°C"} 0.37699053901248425
weewx_temperature_max{period="month",units="°C"} 0.37699053901248425
weewx_temperature_max{period="year",units="°C"} 0.37699053901248425

# HELP weewx_temperature_min Minimum temperature
# TYPE weewx_temperature_min gauge
weewx_temperature_min{period="day",units="°C"} 0.3739623620652803
weewx_temperature_min{period="week",units="°C"} 0.3739623620652803
weewx_temperature_min{period="month",units="°C"} 0.3739623620652803
weewx_temperature_min{period="year",units="°C"} 0.3739623620652803


# ---------- Dewpoint ----------

# HELP weewx_dewpoint_max Maximum dewpoint
# TYPE weewx_dewpoint_max gauge
weewx_dewpoint_max{period="day"} -2.6646883366968006
weewx_dewpoint_max{period="week"} -2.6646883366968006
weewx_dewpoint_max{period="month"} -2.6646883366968006
weewx_dewpoint_max{period="year"} -2.6646883366968006

# HELP weewx_dewpoint_min Minimum dewpoint
# TYPE weewx_dewpoint_min gauge
weewx_dewpoint_min{period="day"} -2.667639882431274
weewx_dewpoint_min{period="week"} -2.667639882431274
weewx_dewpoint_min{period="month"} -2.667639882431274
weewx_dewpoint_min{period="year"} -2.667639882431274


# ---------- Humidity ----------

# HELP weewx_humidity_max Maximum humidity
# TYPE weewx_humidity_max gauge
weewx_humidity_max{period="day"} 79.99999996901272
weewx_humidity_max{period="week"} 79.99999996901272
weewx_humidity_max{period="month"} 79.99999996901272
weewx_humidity_max{period="year"} 79.99999996901272

# HELP weewx_humidity_min Minimum humidity
# TYPE weewx_humidity_min gauge
weewx_humidity_min{period="day"} 79.99999848162298
weewx_humidity_min{period="week"} 79.99999848162298
weewx_humidity_min{period="month"} 79.99999848162298
weewx_humidity_min{period="year"} 79.99999848162298


# ---------- Barometer ----------

# HELP weewx_barometer_max Maximum barometric pressure
# TYPE weewx_barometer_max gauge
weewx_barometer_max{period="day"} 1053.166717356961
weewx_barometer_max{period="week"} 1053.166717356961
weewx_barometer_max{period="month"} 1053.166717356961
weewx_barometer_max{period="year"} 1053.166717356961

# HELP weewx_barometer_min Minimum barometric pressure
# TYPE weewx_barometer_min gauge
weewx_barometer_min{period="day"} 1053.1667156780013
weewx_barometer_min{period="week"} 1053.1667156780013
weewx_barometer_min{period="month"} 1053.1667156780013
weewx_barometer_min{period="year"} 1053.1667156780013


# ---------- Wind ----------

# HELP weewx_wind_speed_max Maximum wind speed
# TYPE weewx_wind_speed_max gauge
weewx_wind_speed_max{period="day"} 9.424525400003968e-08
weewx_wind_speed_max{period="week"} 9.424525400003968e-08
weewx_wind_speed_max{period="month"} 9.424525400003968e-08
weewx_wind_speed_max{period="year"} 9.424525400003968e-08

# HELP weewx_wind_gust_max Maximum wind gust
# TYPE weewx_wind_gust_max gauge
weewx_wind_gust_max{period="day"} 2.63886710273944e-07
weewx_wind_gust_max{period="week"} 2.63886710273944e-07
weewx_wind_gust_max{period="month"} 2.63886710273944e-07
weewx_wind_gust_max{period="year"} 2.63886710273944e-07


# ---------- Rain ----------

# HELP weewx_rain_rate_max Maximum rain rate
# TYPE weewx_rain_rate_max gauge
weewx_rain_rate_max{period="day"} 0.0
weewx_rain_rate_max{period="week"} 0.0
weewx_rain_rate_max{period="month"} 0.0
weewx_rain_rate_max{period="year"} 0.0

# HELP weewx_rain_total Total rainfall
# TYPE weewx_rain_total counter
weewx_rain_total{period="day",units="cm"} 0.0
weewx_rain_total{period="week",units="cm"} 0.0
weewx_rain_total{period="month",units="cm"} 0.0
weewx_rain_total{period="year",units="cm"} 0.0


# ---------- Indoor ----------

# HELP weewx_inside_temperature_max Maximum indoor temperature
# TYPE weewx_inside_temperature_max gauge
weewx_inside_temperature_max{period="day"} 17.222222784584066
weewx_inside_temperature_max{period="week"} 17.222222784584066
weewx_inside_temperature_max{period="month"} 17.222222784584066
weewx_inside_temperature_max{period="year"} 17.222222784584066

# HELP weewx_inside_temperature_min Minimum indoor temperature
# TYPE weewx_inside_temperature_min gauge
weewx_inside_temperature_min{period="day"} 17.222222233698997
weewx_inside_temperature_min{period="week"} 17.222222233698997
weewx_inside_temperature_min{period="month"} 17.222222233698997
weewx_inside_temperature_min{period="year"} 17.222222233698997

# HELP weewx_inside_humidity_max Maximum indoor humidity
# TYPE weewx_inside_humidity_max gauge
weewx_inside_humidity_max{period="day"} 29.999999958683617
weewx_inside_humidity_max{period="week"} 29.999999958683617
weewx_inside_humidity_max{period="month"} 29.999999958683617
weewx_inside_humidity_max{period="year"} 29.999999958683617

# HELP weewx_inside_humidity_min Minimum indoor humidity
# TYPE weewx_inside_humidity_min gauge
weewx_inside_humidity_min{period="day"} 29.999997975497358
weewx_inside_humidity_min{period="week"} 29.999997975497358
weewx_inside_humidity_min{period="month"} 29.999997975497358
weewx_inside_humidity_min{period="year"} 29.999997975497358
```