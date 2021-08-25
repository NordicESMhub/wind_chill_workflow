# Windchill_workflow
Compute wind chill from weather forecasts surface temperature and wind speed.

We will be using the [Canada's Wind chill Index](https://www.canada.ca/en/environment-climate-change/services/weather-health/wind-chill-cold-weather/wind-chill-index.html). As mentioned on their website, it reflects the needs of Canadians so we can probably consider it accurate for the Nordic countries too.

The CWI (Canada's Wind chill Index) is given in degrees Celcius and is equivalent to the temperature with no wind. It represents the degree of "chill" that your skin senses. For example, if the wind chill is -20 while the outside temperature is only -10ºC, it means that your face will feel as cold as if it was a calm day (no wind) with a temperature of -20ºC.

We can use the following formula to compute CWI:

<img src="https://render.githubusercontent.com/render/math?math=WCI = 13.12 %2B  0.6215 * T_{air} - 11.37 * V^{0.16} %2B 0.3965 * T_{air} * V^{0.16}">

Where:
- <img src="https://render.githubusercontent.com/render/math?math=T_{air}"> is the 2 meter temperature in degrees Celcius (we do not take the temperature at the surface because it would give us the temperature of the soil and not the air temperature).
- <img src="https://render.githubusercontent.com/render/math?math=V"> is the 10 meter wind speed in kilometer per hour (like for the temperature, we do not take the wind speed at the surface but at 10 meter height)

**[Important Benchmarks](http://www.medicine.mcgill.ca/epidemiology/hanley/c609/Material/CanadaWindChill.pdf)**
-  -27 C: Risk of frostbite in prolonged exposures (similar to previous 1800 watts/m2)
-  -35 C: Frostbite possible in 10-15 minutes (similar to previous 2000 watts/m2)
-  -40 C: Wind chill warning will be issued. Frostbite possible in less than 10 minutes (similar to the previous 2200 watts/m2)
-  -45 C: Be ready to cut short or cancel outdoor activities. Frostbite possible in minutes.
-  -60 C: DANGER! Frostbite possible in under 2 minutes (similar to 2700 watts/m2)
