# Gun Violence in the U.S.
<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#inspiration-for-the-project">Inspiration for the Project</a></li>
    <li><a href="#built-with">Built With</a></li>
    <li><a href="#getting-started">Getting Started</a></li>
  </ol>
</details>

<!--
    <li>
      <a href="#user-interface-walkthrough">User Interface Walkthrough</a>
      <ul>
        <li><a href="#search-criteria-and-filters">Search Criteria and Filters</a></li>
        <li><a href="#view-more-flight-information">View More Flight Information</a></li>
        <li><a href="#reschedule-a-flight">Reschedule a Flight</a></li>
        <li><a href="#cancel-a-flight">Cancel a Flight</a></li>
      </ul>
    </li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
-->

## Inspiration for the Project

My inspiration for performing this analysis stems back to my time during undergrad at the University of Florida. I was taking an introductory data analysis course, and as our final project, we had to analyze this specific dataset. At the time, I primarily used Excel to perform my analysis. Now having a greater understanding of other languages such as Python and R, I decided to revisit and further investigate the data.

My primary goal with my exploration is to discover hidden trends in the dataset, and provide clear and meaningful visualizations of my analysis.

## Built With

## Getting Started

## Overview of the Dataset
This dataset is a comprehensive documentation of over 260k US gun violence incidents from 2013 to 2018. Each record includes information with regards to a particular gun-related incident such as the state and city where the incident occurred, descriptions of the incident participants, the number of individuals injured or killed, and the type of guns involved. Feel free to visit [this page](https://www.kaggle.com/jameslko/gun-violence-data) to view the original dataset.

<bound method DataFrame.to_markdown of         incident_id        date           state city_or_county  \
195393       879798  2017-06-28  South Carolina    Hardeeville   
236431      1067771  2018-03-11         Alabama      Sheffield   
101368       456687  2015-12-01        New York        Oneonta   
128028       592713  2016-05-27   New Hampshire      Rochester   
154312       713088  2016-11-01   West Virginia     Clarksburg   

                            address  n_killed  n_injured  \
195393  1200 block of Plantation Dr         0          0   
236431                          NaN         1          0   
101368                          NaN         0          1   
128028            North Main Street         0          0   
154312                          NaN         0          0   

                                             incident_url  \
195393  http://www.gunviolencearchive.org/incident/879798   
236431  http://www.gunviolencearchive.org/incident/106...   
101368  http://www.gunviolencearchive.org/incident/456687   
128028  http://www.gunviolencearchive.org/incident/592713   
154312  http://www.gunviolencearchive.org/incident/713088   

                                               source_url  \
195393  http://www.jaspersuntimes.com/news/2017-06-29/...   
236431  http://www.timesdaily.com/news/sheffield-counc...   
101368  http://www.thedailystar.com/news/local_news/un...   
128028  http://www.fosters.com/news/20160629/rochester...   
154312  https://www.justice.gov/usao-ndwv/pr/ohio-man-...   

        incident_url_fields_missing  congressional_district  \
195393                        False                     6.0   
236431                        False                     4.0   
101368                        False                    19.0   
128028                        False                     1.0   
154312                        False                     1.0   

                                gun_stolen  \
195393  0::Unknown||1::Unknown||2::Unknown   
236431                          0::Unknown   
101368                          0::Unknown   
128028                                 NaN   
154312                          0::Unknown   

                                  gun_type  \
195393  0::Shotgun||1::Handgun||2::Handgun   
236431                          0::Unknown   
101368                          0::Handgun   
128028                                 NaN   
154312                            0::40 SW   

                                 incident_characteristics  latitude  \
195393  Non-Shooting Incident||Drug involvement||ATF/L...   32.2681   
236431  Shot - Dead (murder, accidental, suicide)||Sui...   34.7592   
101368  Non-Shooting Incident||Home Invasion||Home Inv...   42.4866   
128028                           Gun(s) stolen from owner   43.3073   
154312  Non-Shooting Incident||Drug involvement||Posse...   39.2776   

       location_description  longitude  n_guns_involved  \
195393                  NaN   -81.0556              3.0   
236431                  NaN   -87.6941              1.0   
101368                  NaN   -75.0758              1.0   
128028                  NaN   -70.9872              NaN   
154312                  NaN   -80.3407              1.0   

                                                    notes participant_age  \
195393  Jasper Co, cash, drugs, 3 guns incl shotgun, a...    0::51||1::40   
236431                                                NaN             NaN   
101368  threat res with handgun, pw during robbery, un...           1::27   
128028                                  gun report stolen             NaN   
154312                                         Court date           0::42   

             participant_age_group participant_gender  \
195393  0::Adult 18+||1::Adult 18+   0::Male||1::Male   
236431                0::Adult 18+            0::Male   
101368                1::Adult 18+            1::Male   
128028                         NaN                NaN   
154312                0::Adult 18+            0::Male   

                           participant_name participant_relationship  \
195393  0::Charles Carr||1::Trevier Johnson                      NaN   
236431                       0::Gary Scales                      NaN   
101368                   1::Jason R Cousins                      NaN   
128028                                  NaN                      NaN   
154312              0::Johnny D. Floyd, Sr.                      NaN   

                                  participant_status  \
195393  0::Unharmed, Arrested||1::Unharmed, Arrested   
236431                                     0::Killed   
101368             0::Injured||1::Unharmed, Arrested   
128028                                           NaN   
154312                         0::Unharmed, Arrested   

                              participant_type  \
195393  0::Subject-Suspect||1::Subject-Suspect   
236431                               0::Victim   
101368           0::Victim||1::Subject-Suspect   
128028                                     NaN   
154312                      0::Subject-Suspect   

                                                  sources  \
195393  http://www.jaspersuntimes.com/news/2017-06-29/...   
236431  http://www.timesdaily.com/news/sheffield-counc...   
101368  http://www.thedailystar.com/news/local_news/un...   
128028  http://www.fosters.com/news/20160629/rochester...   
154312  https://www.justice.gov/usao-ndwv/pr/ohio-man-...   

        state_house_district  state_senate_district  
195393                 118.0                   45.0  
236431                   3.0                    6.0  
101368                 121.0                   51.0  
128028                   NaN                    6.0  
154312                  48.0                   12.0  >
