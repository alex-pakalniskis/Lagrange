---
layout: post
title: "Measuring the Last Mile"
author: "Alex Pakalniskis"
categories: journal
tags: [micromobility,bike share, open data, pandas, GeoViews, geopandas, glob, numpy, scipy, matplotlib, pyplot]
image: bike-stop-map.png

---

# Measuring the Last Mile
## Bike-Share Ridership Trends from LA County Metro

Despite advances in public transportation infrastructure, intense road congestion and poor service schedules force many urban residents to adopt mixed-modes of transportation during a single trip out. Innovative ride-sharing applications have disrupted the transportation *status quo*, but ride-shares remain plagued by the same automotive gridlock experienced by private cars and public transit alike. The new wave of single-passenger transportation solutions aims to ease the burden of this so-called "[last mile](https://en.wikipedia.org/wiki/Last_mile_(transportation))" problem. 

Communal, light-weight personal vehicles such as electric scooters, mopeds, and bicycles are popping up across major world cities. In many cases, residents are able to purchase these last-mile services from a variety of public and private providers (with short and long-term committment options). As residents navigate the micromobility landscape, finding a suitable solution depends on factors including vehicle type, rental pricing, and availability. Committment periods ranging from a few hours to a whole year provide a variety of options for consumers, but may not suit all lifestyles. A casual-but-regular weekend rider is left to purchase more expensive walk-up plans for their weekly rides as a monthly or yearly plan may not be justifiable. 

Balancing private competitors, the needs of residents, and future development, public service providers are in a unique position in the micromobility market. However, as a pubic institution the main goal ought to be serving residents and fulfilling their needs. As open data initiatives proliferate across global municipalities, millions of light-vehicle trip logs from municipal service providers are being released to the public domain. While data are anonymized for rider privacy, trip records can provide valuable insights into the lifestyles and needs of shared light-vehicle users. Ultimately, this is an opportunity to apply data-driven insights to better serve residents and customers.

In light of the increasing ubiquity of micromobility services in cities, this project investigates the relationship between plan type and usage patterns in Los Angeles County's [Metropolitan Transportation Authority](https://www.metro.net/) bike-share network. 


![bike share](https://live.staticflickr.com/4315/35824433242_3a5d4983c2_b.jpg)

**Source**: Flickr, [Paul Wasneski](https://www.flickr.com/photos/paulwasneski/)
