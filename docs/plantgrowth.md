## County Climate Impacts project: plant growth impact

This note describes some aspects of work in the plant growth impact strand of the County Climates Impacts project.

### Choice of future climate projection

Climate models require values for variables which affect climate (such as levels of greenhouse gas emissions and land use change).  For projections of future climate change, these values have to be assumed (because we don't know what they'll be in the future - unlike in the past).  These assumptions take the form of so-called *representative concentration pathways* (rcps), and the projections are usually modelled for different rcps - essentially giving different alternative future climates.  The rcp we're using is rcp585, which is the ["business as usual" scenario](https://www.carbonbrief.org/explainer-the-high-emissions-rcp8-5-global-warming-scenario) (i.e. no decrease in emissions from present day trends), and so shows the highest levels of warming (compared to other rcps).  

Essentially, we're using rcp85 because it's the only one available for the *regional* projections from UKCP18, and we're using these projections because (we think) that's the optimum spatial resolution (12km) for county impacts.  Other rcps are available (corresponding to more stringent restrictions on greenhouse gas emissions), but for less suitable resolutions in UKCP18.

### Choice of temperature data

This strand was (originally) interested in forging a link between climate change data and plant growth - specifically, via the so-called [plant hardiness ratings](https://www.rhs.org.uk/plants/trials-awards/award-of-garden-merit/rhs-hardiness-rating) which denote the temperature range required for a given plant (or class of plants) to flourish.  The focus of this rating is on miniumum temperatures (e.g. the effect of frost), so we first looked at projections for ***tasmin***, the minimum near-surface air temperature.  We extracted the mean monthly minumum surface air temperature for the month of February (assuming that to be the coldest month in the UK) from the UKCP18 data on the 12 km grid for the first ensemble member.  Initially, this was done for the years [1980-2080](https://github.com/mo-simoneaton/county-climate-impacts/blob/master/data/tasmin_rcp85_land-rcm_uk_12km_01_mon_1980-2080_Feb.nc), and then for the three periods of interest 

* [1995-2000](https://github.com/mo-simoneaton/county-climate-impacts/blob/master/data/tasmin_rcp85_land-rcm_uk_12km_01_mon_1995-2000_Feb.nc)
* [2025-2030](https://github.com/mo-simoneaton/county-climate-impacts/blob/master/data/tasmin_rcp85_land-rcm_uk_12km_01_mon_2025-2030_Feb.nc)
* [2055-2060](https://github.com/mo-simoneaton/county-climate-impacts/blob/master/data/tasmin_rcp85_land-rcm_uk_12km_01_mon_2055-2060_Feb.nc)

The routine used to do the extraction was [getMinTemp.py](https://github.com/mo-simoneaton/county-climate-impacts/blob/master/getMinTemp.py), which uses the [Iris package](https://scitools-iris.readthedocs.io/en/stable/) to read and manipulate the climate data.

### Choice of ensemble member(s)

Initial focus was on a single member of the UKCP18 ensemble; a more rigorous treatment would use the ensemble average.