---
layout: post
title: "Measuring the Last Mile"
author: "Alex Pakalniskis"
categories: journal
tags: [micromobility,bike share, open data, pandas, GeoViews, geopandas, glob, numpy, scipy, matplotlib, pyplot]
image: bike-stop-map.png

---
*Los Angeles County Metropolitan Transportation Authority Bike-Share Docks (2016-2019)*

Despite advances in public transportation infrastructure, intense road congestion and poor service schedules force many urban residents to adopt mixed-modes of transportation during a single trip out. Innovative ride-sharing applications have disrupted the transportation *status quo*, but ride-shares remain plagued by the same automotive gridlock experienced by private cars and public transit alike. The new wave of single-passenger transportation solutions aims to ease the burden of this so-called "[last mile](https://en.wikipedia.org/wiki/Last_mile_(transportation))" problem. 

![bike share in washington dc](https://upload.wikimedia.org/wikipedia/commons/thumb/1/13/Capital_Bikeshare_DC_2010_10_532.JPG/1280px-Capital_Bikeshare_DC_2010_10_532.JPG)

**Source**: [Wikipedia, Last mile (transportation)](https://en.wikipedia.org/wiki/Last_mile_(transportation))

Communal, light-weight personal vehicles such as electric scooters, mopeds, and bicycles are popping up across major world cities. In many cases, residents are able to purchase these last-mile services from a variety of public and private providers (with short and long-term commitment options). As residents navigate the micromobility landscape, finding a suitable solution depends on factors including vehicle type, rental pricing, and availability. Commitment periods ranging from a few hours to a whole year provide a variety of options for consumers, but may not suit all lifestyles. A casual-but-regular weekend rider is left to purchase more expensive walk-up plans for their weekly rides as a monthly or yearly plan may not be justifiable. 

![metro-bike-share rider](https://11ka1d3b35pv1aah0c3m9ced-wpengine.netdna-ssl.com/wp-content/uploads/2018/09/DSC01282.jpg)

**Source**: [LA Metro Bike Share](https://bikeshare.metro.net/)

Balancing private competitors, the needs of residents, and future development, public service providers are in a unique position in the micromobility market. However, as a pubic institution the main goal ought to be serving residents and fulfilling their needs. As open data initiatives proliferate across global municipalities, millions of light-vehicle trip logs from municipal service providers are being released to the public domain. While data are anonymized for rider privacy, trip records can provide valuable insights into the lifestyles and needs of shared light-vehicle users. Ultimately, this is an opportunity to apply data-driven insights to better serve residents with additional commitment plans that fit their lifestyles.

In light of the increasing ubiquity of micromobility services in cities, this project investigates the relationship between plan type and usage patterns in Los Angeles County's [Metropolitan Transportation Authority](https://www.metro.net/) bike-share network. While LA Metro divides pass holders into fairly nuanced categories (i.e. daily pass, monthly pass, etc.), cities such as [New York](https://www.citibikenyc.com/system-data) and [Chicago](https://www.divvybikes.com/system-data) employ a coarser approach to grouping users ("Customer" or "Subscriber"). I chose to apply this common "Customer" vs "Subscriber" dichotomy for my analysis so that future work may include results in comparative surveys of multiple cities or network types. 

### Questions

* Is average trip length affected by plan type?
* Do weekly ridership patterns vary by plan type?

"Subscribers" comprise 64% of the total rides taken (1.8 million), with "Customers" riding the remaining 36%. On average, "Customer" bike trips are 3.5 times as long as "Subscriber" trips. Calculated using two random samples of 50,000 trips (one for each user type), this difference of 14 vs. 48 minutes roughly translates into 2.25 or 8 miles at a 10 miles per hour pace. While data privacy prevents more nuanced investigations in rider trip paths, these findings suggests that plan type may be a contributing factor determinging bike-share trip length. However, this is only speculation without knowing the distance traveled for each trip. Customers could very well stop-and-go, attaining an average cruising speed of 3 miles per hour while traveling 2.4 miles.  
 
![average trip durations by bike-share user type in LA Metro, 2016-2019](/assets/img/metro-bike-share-trip-duration.png)

A survey of all bike trips (except those longer than 24 hours or outside Los Angeles boundaries) indicates that "Subscribers" tend to ride on weekdays (Monday-Friday), while "Customers" are more evenly split in weekly riding habits. 

![ride daytypes by bike-share user type in LA Metro, 2016-2019](/assets/img/metro-bike-share-ride-day-types.png)

These results suggest that riders could benefit from some different committment options than currently available. More specialized plans targetting lifestyles instead of time periods may better suit the needs of bike-share riders. Weekday-only plans, where riders don't have access to vehicles on weekends, would suit the numerous subscribers who only ride to or from work on weekdays. Similarly, a weekend-only plan could significantly reduce costs for "Customers" unable to justify current plans (monthly or annual) given their infrequent-but-cyclical usage. 

Quantitative studies of anonymized data can provide insights into generalized rider trends, and additional studies should investigate additional rider attributes. However, qualitative surveys of actual riders will benefit both the riders and the providers. Data anonymity prevents analysis of "Customer" return frequency, so the true potential for conversion from "Customer" to "Subscriber" is unknown at this time. Similarly, the total distance traveled during each trip is not avaialble at this time, but it release would clarify uncertainties in the data. Converting even a small portion of the 35% of "Customers" to "Subscribers" could result in additional profits for the provider and improved service for the riders, but none of it will be possible without asking the riders what they want.  
