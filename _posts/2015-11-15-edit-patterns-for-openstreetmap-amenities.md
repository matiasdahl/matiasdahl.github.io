---
layout:       post
asset-dir:    /assets/2015/edit-patterns-for-openstreetmap-amenities/
title:        Edit patterns for OpenStreetMap amenities
date:         2015-11-15 23:00
---

The [extract-amenities](https://github.com/matiasdahl/osm-amenities-export) script outputs all the map elements in an [OpenStreetMap](https://www.openstreetmap.org/) file that have an `amenity=..`-tag. Also, if an element has multiple versions, all versions are extracted starting from the first version with an `amenity=..`-tag. An example of how to load and work with this data in R can be found [here](https://matiasdahl.github.io/blog/2015/loading-openstreetmap-amenity-data-into-r/). The purpose of this analysis is to use the same amenity data (the full export from 10.8.2015) and plot the edit intensity patterns for the top-75 amenities. These roughly correspond to those amenities with more than 5000 unique map elements when counted over the entire history of the OSM, that is, when we also include map elements that are currently deleted.

There are two plots for each amenity:

**Edit intensity:** In the first plot, the *x*-axis represents time, the *y*-axis represents all the map elements with a specific amenity tag, and edits are represented by points whose darkness increase with edit intensity. On the *y*-axis, the elements are ordered chronologically by the date a first `amenity=..` tag was added to a map element. Due to the large number of map elements, the data in these plots is highly compressed. For example, the first plot visualizes the ca. 2 million unique map elements that have ever had an `amenity=parking`-tag, and on-screen these are mapped onto ca. 500-1000 pixels. 

**Edits/month:** For each amenity, the second plot shows the total number of edits per month. 

## Notes

- In the edit intensity plots, the *y*-scale is linear and time is discretized by week. In the edits/month plots, the *y*-scale is logarithmic and time is discretized by month. In both plots, deleting and undeleting are counted as edits. So, if an map element was added in 2009 and deleted in 2010, the element would only contribute to the activity for those years. Also, if the amenity tag of an element is changed, say, from `amenity=cafe` to `amenity=restaurant`, the element appears in the plots for both tags.

- Many of the intensity plots show growth by large jumps and contain dark vertical lines. These should correspond to database imports/automatic edits by bots, see the [OSM wiki](http://wiki.openstreetmap.org/wiki/Import). The plots indicate that elements that have been imported from databases typically have a lower edit intensity when compared to normal entries. In the plots, this is seen as lighter horizontal bands at the location of the vertical jumps. See for example the plot for the amenity `school` (at rank 2). 

- The first plot visualizes more than 3.6 million edits to the OpenStreetMap, and the last plot around 12000. These are different orders of magnitude, and therefore the plots are also drawn with slightly different plotting parameters. This is to improve readability and contrast. As a consequence, the absolute shades in different plots are not comparable. 

- In the intensity plots, the region close to the creation date is often darker than average. This behavior can be seen in the first few plots (with the most map elements). This would suggest that an element is more frequently edited shortly after it has been created. However, in the intensity plots with fewer elements, this is not visible. This could be due to the way the plots are rendered (see previous note).

- Some of the graphs show a clear seasonal variation. See e.g. the plots for `bench` (rank 5) and `biergarten` (rank 63).

## Plots




#### Amenity: [parking](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dparking) (rank 1, unique elements = 2.1M)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_parking-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_parking-1.png) 
 
#### Amenity: [school](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dschool) (rank 2, unique elements = 903.6k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_school-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_school-1.png) 
 
#### Amenity: [place_of_worship](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dplace_of_worship) (rank 3, unique elements = 891.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_place_of_worship-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_place_of_worship-1.png) 
 
#### Amenity: [restaurant](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Drestaurant) (rank 4, unique elements = 598.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_restaurant-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_restaurant-1.png) 
 
#### Amenity: [bench](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbench) (rank 5, unique elements = 526.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_bench-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_bench-1.png) 
 
#### Amenity: [fuel](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dfuel) (rank 6, unique elements = 349.3k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_fuel-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_fuel-1.png) 
 
#### Amenity: [bank](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbank) (rank 7, unique elements = 220.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_bank-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_bank-1.png) 
 
#### Amenity: [kindergarten](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dkindergarten) (rank 8, unique elements = 218.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_kindergarten-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_kindergarten-1.png) 
 
#### Amenity: [fast_food](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dfast_food) (rank 9, unique elements = 218.6k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_fast_food-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_fast_food-1.png) 
 
#### Amenity: [cafe](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcafe) (rank 10, unique elements = 218.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_cafe-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_cafe-1.png) 
 
#### Amenity: [post_box](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dpost_box) (rank 11, unique elements = 200.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_post_box-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_post_box-1.png) 
 
#### Amenity: [hospital](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dhospital) (rank 12, unique elements = 199.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_hospital-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_hospital-1.png) 
 
#### Amenity: [grave_yard](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dgrave_yard) (rank 13, unique elements = 189.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_grave_yard-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_grave_yard-1.png) 
 
#### Amenity: [public_building](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dpublic_building) (rank 14, unique elements = 179.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_public_building-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_public_building-1.png) 
 
#### Amenity: [pharmacy](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dpharmacy) (rank 15, unique elements = 166.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_pharmacy-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_pharmacy-1.png) 
 
#### Amenity: [recycling](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Drecycling) (rank 16, unique elements = 164.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_recycling-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_recycling-1.png) 
 
#### Amenity: [post_office](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dpost_office) (rank 17, unique elements = 153.4k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_post_office-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_post_office-1.png) 
 
#### Amenity: [pub](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dpub) (rank 18, unique elements = 149.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_pub-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_pub-1.png) 
 
#### Amenity: [bicycle_parking](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbicycle_parking) (rank 19, unique elements = 137.9k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_bicycle_parking-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_bicycle_parking-1.png) 
 
#### Amenity: [waste_basket](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dwaste_basket) (rank 20, unique elements = 137.6k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_waste_basket-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_waste_basket-1.png) 
 
#### Amenity: [toilets](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dtoilets) (rank 21, unique elements = 130.3k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_toilets-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_toilets-1.png) 
 
#### Amenity: [shelter](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dshelter) (rank 22, unique elements = 129.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_shelter-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_shelter-1.png) 
 
#### Amenity: [police](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dpolice) (rank 23, unique elements = 109.2k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_police-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_police-1.png) 
 
#### Amenity: [swimming_pool](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dswimming_pool) (rank 24, unique elements = 104.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_swimming_pool-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_swimming_pool-1.png) 
 
#### Amenity: [drinking_water](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Ddrinking_water) (rank 25, unique elements = 104.7k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_drinking_water-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_drinking_water-1.png) 
 
#### Amenity: [telephone](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dtelephone) (rank 26, unique elements = 102.7k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_telephone-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_telephone-1.png) 
 
#### Amenity: [atm](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Datm) (rank 27, unique elements = 101.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_atm-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_atm-1.png) 
 
#### Amenity: [fire_station](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dfire_station) (rank 28, unique elements = 99.4k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_fire_station-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_fire_station-1.png) 
 
#### Amenity: [bar](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbar) (rank 29, unique elements = 97.2k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_bar-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_bar-1.png) 
 
#### Amenity: [townhall](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dtownhall) (rank 30, unique elements = 94.6k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_townhall-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_townhall-1.png) 
 
#### Amenity: [university](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Duniversity) (rank 31, unique elements = 83.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_university-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_university-1.png) 
 
#### Amenity: [parking_space](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dparking_space) (rank 32, unique elements = 80.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_parking_space-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_parking_space-1.png) 
 
#### Amenity: [library](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dlibrary) (rank 33, unique elements = 70.4k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_library-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_library-1.png) 
 
#### Amenity: [hunting_stand](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dhunting_stand) (rank 34, unique elements = 69.3k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_hunting_stand-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_hunting_stand-1.png) 
 
#### Amenity: [fountain](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dfountain) (rank 35, unique elements = 66.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_fountain-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_fountain-1.png) 
 
#### Amenity: [vending_machine](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dvending_machine) (rank 36, unique elements = 65.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_vending_machine-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_vending_machine-1.png) 
 
#### Amenity: [doctors](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Ddoctors) (rank 37, unique elements = 57.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_doctors-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_doctors-1.png) 
 
#### Amenity: [social_facility](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dsocial_facility) (rank 38, unique elements = 54.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_social_facility-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_social_facility-1.png) 
 
#### Amenity: [bus_station](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbus_station) (rank 39, unique elements = 54.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_bus_station-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_bus_station-1.png) 
 
#### Amenity: [college](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcollege) (rank 40, unique elements = 48.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_college-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_college-1.png) 
 
#### Amenity: [nursing_home](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dnursing_home) (rank 41, unique elements = 43.7k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_nursing_home-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_nursing_home-1.png) 
 
#### Amenity: [car_wash](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcar_wash) (rank 42, unique elements = 40.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_car_wash-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_car_wash-1.png) 
 
#### Amenity: [marketplace](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dmarketplace) (rank 43, unique elements = 37.4k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_marketplace-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_marketplace-1.png) 
 
#### Amenity: [community_centre](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcommunity_centre) (rank 44, unique elements = 32.3k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_community_centre-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_community_centre-1.png) 
 
#### Amenity: [dentist](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Ddentist) (rank 45, unique elements = 31.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_dentist-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_dentist-1.png) 
 
#### Amenity: [emergency_phone](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Demergency_phone) (rank 46, unique elements = 30.9k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_emergency_phone-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_emergency_phone-1.png) 
 
#### Amenity: [waste_disposal](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dwaste_disposal) (rank 47, unique elements = 30.7k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_waste_disposal-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_waste_disposal-1.png) 
 
#### Amenity: [theatre](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dtheatre) (rank 48, unique elements = 30.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_theatre-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_theatre-1.png) 
 
#### Amenity: [fire_hydrant](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dfire_hydrant) (rank 49, unique elements = 26.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_fire_hydrant-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_fire_hydrant-1.png) 
 
#### Amenity: [residential](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dresidential) (rank 50, unique elements = 26.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_residential-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_residential-1.png) 
 
#### Amenity: [wlan](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dwlan) (rank 51, unique elements = 26.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_wlan-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_wlan-1.png) 
 
#### Amenity: [cinema](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcinema) (rank 52, unique elements = 25.2k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_cinema-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_cinema-1.png) 
 
#### Amenity: [taxi](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dtaxi) (rank 53, unique elements = 23.7k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_taxi-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_taxi-1.png) 
 
#### Amenity: [bicycle_rental](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbicycle_rental) (rank 54, unique elements = 22.3k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_bicycle_rental-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_bicycle_rental-1.png) 
 
#### Amenity: [clinic](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dclinic) (rank 55, unique elements = 21.9k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_clinic-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_clinic-1.png) 
 
#### Amenity: [parking_entrance](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dparking_entrance) (rank 56, unique elements = 19.9k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_parking_entrance-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_parking_entrance-1.png) 
 
#### Amenity: [veterinary](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dveterinary) (rank 57, unique elements = 17.7k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_veterinary-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_veterinary-1.png) 
 
#### Amenity: [arts_centre](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Darts_centre) (rank 58, unique elements = 15.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_arts_centre-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_arts_centre-1.png) 
 
#### Amenity: [courthouse](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcourthouse) (rank 59, unique elements = 15.4k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_courthouse-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_courthouse-1.png) 
 
#### Amenity: [nightclub](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dnightclub) (rank 60, unique elements = 15.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_nightclub-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_nightclub-1.png) 
 
#### Amenity: [ferry_terminal](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dferry_terminal) (rank 61, unique elements = 14.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_ferry_terminal-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_ferry_terminal-1.png) 
 
#### Amenity: [bbq](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbbq) (rank 62, unique elements = 12.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_bbq-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_bbq-1.png) 
 
#### Amenity: [biergarten](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbiergarten) (rank 63, unique elements = 10.9k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_biergarten-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_biergarten-1.png) 
 
#### Amenity: [car_rental](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcar_rental) (rank 64, unique elements = 10.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_car_rental-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_car_rental-1.png) 
 
#### Amenity: [grit_bin](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dgrit_bin) (rank 65, unique elements = 9.4k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_grit_bin-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_grit_bin-1.png) 
 
#### Amenity: [embassy](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dembassy) (rank 66, unique elements = 9.2k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_embassy-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_embassy-1.png) 
 
#### Amenity: [prison](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dprison) (rank 67, unique elements = 8.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_prison-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_prison-1.png) 
 
#### Amenity: [shower](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dshower) (rank 68, unique elements = 8.1k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_shower-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_shower-1.png) 
 
#### Amenity: [clock](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dclock) (rank 69, unique elements = 8.0k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_clock-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_clock-1.png) 
 
#### Amenity: [driving_school](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Ddriving_school) (rank 70, unique elements = 7.2k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_driving_school-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_driving_school-1.png) 
 
#### Amenity: [charging_station](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcharging_station) (rank 71, unique elements = 6.9k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_charging_station-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_charging_station-1.png) 
 
#### Amenity: [ice_cream](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dice_cream) (rank 72, unique elements = 6.8k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_ice_cream-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_ice_cream-1.png) 
 
#### Amenity: [car_sharing](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dcar_sharing) (rank 73, unique elements = 6.5k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_car_sharing-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_car_sharing-1.png) 
 
#### Amenity: [bus_stop](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbus_stop) (rank 74, unique elements = 5.9k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_bus_stop-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_bus_stop-1.png) 
 
#### Amenity: [unterschiedlich](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dunterschiedlich) (rank 75, unique elements = 5.3k)

![](/assets/2015/edit-patterns-for-openstreetmap-amenities/int_unterschiedlich-1.png) 
![](/assets/2015/edit-patterns-for-openstreetmap-amenities/month_unterschiedlich-1.png) 
 

## OSM License 

The above analysis contains data from the OpenStreetMap project, (c) OpenStreetMap contributors. The OSM data is available under the [ODbL](https://www.openstreetmap.org/copyright). The R code for this analysis is available on [Github](https://github.com/matiasdahl/osm-extract-amenities-r/).

