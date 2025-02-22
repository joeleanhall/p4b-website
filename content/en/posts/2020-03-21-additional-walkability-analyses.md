---
layout: post
title: Additional walkability analyses
author: jehle
lang: en
tags:
- en
categories:
- news
- development
thumbnail: "/images/blog/additional_walkability_analyses/scenery_hasenbergl-thumbnail.webp"
image: "/images/blog/additional_walkability_analyses/scenery_hasenbergl-banner.webp"
summary: In order to create livable cities and shape a more sustainable mobility,
  it is crucial to focus on walkable environments. However, the quality of the infrastructure
  depends highly on the individual.
date: 2020-03-21

---
## Creating livable spaces

_- This blogpost gives a summary of my Master Thesis. If interested in more details, the complete document can be downloaded below. -_

In order to create livable cities and shape a more sustainable mobility, it is crucial to focus on walkable environments. However, the quality of the infrastructure depends highly on the individual. For example, one-third of the German population is temporarily mobility impaired and 28% of the population is over 60 years old, which results in different requirements, such as smooth surfaces and barrier-free footpaths. To provide good walking accessibility, all these different needs must be considered in the planning processes, which makes providing appropriate infrastructure quite a complex challenge.

## The four accessibility components

Accessibility instruments as planning support systems can help to face these challenges. Ideally, all four components of accessibility (land-use component, transportation component, temporal component, individual component) are included in an accessibility instrument. This thesis examines, how those four components can be included in GOAT. To realize this, the four accessibility component schema with the associated attributes was applied to GOAT, as shown in the following figure.

![Associated attributes of the accessibility components applied to GOAT](/images/blog/additional_walkability_analyses/four_accessibility_components.webp "Four accessibility components")

(adapted from Geurs and van Wee 2004)

## Data collection

„Hasenbergl-Lerchenau“, one of Munichs’s districts with the lowest average income, with a size of 869 ha and 46,953 inhabitants, was chosen as the study area. All necessary data was captured in OpenStreetMap (OSM) using the iOS app “Go Map!!”, JOSM and Mapillary. Although the OSM-data in the study area was mostly geometrically correct and features such as the street network and buildings were almost completely mapped, for this study essential attributes were missing. For example, only 5% of all paths had information on illuminance and only 3% of the roads had information on sidewalk availability. After 20 days of on-site mapping and off-site data preparation, all 2,000 existing paths with a total length of over 200 km were recorded in OSM. Including information on road type, width, surface, incline, sidewalk availability, illumination and wheelchair accessibility. Likewise, wheelchair accessibility was recorded for all POIs. Therewith, data quality could be highly improved (see chapter 6.3. of this thesis).

![Two buildings by the water in Hasenbergl-Lerchenau](/images/blog/additional_walkability_analyses/scenery_hasenbergl.webp "Hasenbergl-Lerchenau")

## Individual and temporal analyzes

With the improved data, new options could be provided in GOAT. To represent the individual and the temporal component, three new routing profiles (elderly, wheelchair, safe-night) that influence the route choice and walking speed, were implemented. The wheelchair routing only considers barrier-free paths and destinations while the safe-night routing only makes use of paths that are illuminated at night. Furthermore, the opening hours of POIs were included to allow for time-based accessibility analysis (more detailed information can be found in chapter 7).

The analysis of the gathered data manifests that there is a high share of unlit and non-barrier-free ways in the study area, that do serve as important links for pedestrians. The following figure shows a comparison in accessibility between standard and safe-night routing from a starting point within a residential area using a 7-minutes walking isochrone. The contraction of the isochrone indicates that accessibility is significantly reduced if this temporal component is considered.

![Walking accessibility using standard and safe-night routing compared](/images/blog/additional_walkability_analyses/comparison_walking_accessibility.webp "Comparison walking accessibility")

Similar results are obtained for the barrier-free routing. In addition, it was found that many POIs are not accessible at all to persons with mobility impairments, usually because of steps at the entrance. By calculating multi-isochrones, wheelchair accessibility of important amenities, for example of doctors, can be evaluated. The following video shows the comparison of the standard 10-minutes walking catchment area around all doctors and the same area using the wheelchair routing profile. The results are that approximately 8,880 persons out of a total population of 46,950 do not have barrier-free access to a doctor within a 10-minute walking distance. More analyses are provided in chapter 9 of the thesis.

<iframe class="embed-responsive-item" src="https://player.vimeo.com/video/399481443" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen data-uk-responsive width="1920" height="1080"></iframe>

## Visualization of walkability criteria

Furthermore, the frontend was adjusted to include new layers on different walkability criteria (illumination, wheelchair usability, footpath width, surface, number of lanes, maximum speed, parking, street crossings and street furniture), which visualizes the transportation component more realistically (see chapter 8). These layers provide the user with useful information and allow to easily identify weak points in the footpath network. As the objectively measured street level quality criteria cannot cover the entire concept of walkability, also self-reported statements by pedestrians about their perceived walking quality were included to provide a more comprehensive picture. This turned out to be particularly valuable, as the perceived quality often differs from the objectively measured quality.

## Conclusion

With the realized changes, all four accessibility components could be incorporated in GOAT. These improvements provide useful insights into how different groups of people are influenced in their walking accessibility by changes in the temporal and individual components. Therewith, GOAT was enhanced to provide more holistic accessibility analyses. But these analysis options depend heavily on data availability. Therefore, not all new features are by default integrated in GOAT. Depending on the local context, the features can be enabled or disabled.

This implementation should be seen as first attempt to better model the temporal and individual component of accessibility for pedestrians, but further improvements will be realized in the future. We are also very open to your feedback!

This version for Hasenbergl-Lerchenau contains all new features and can be tested [here](https://hasenbergl.open-accessibility.org/).

Furthermore, the complete Thesis can be downloaded [here](https://mediatum.ub.tum.de/604993?query=Ulrike+Jehle&show_id=1542813).