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

| incident_id | date | state | city_or_county | address | n_killed | n_injured | incident_url | source_url | incident_url_fields_missing | congressional_district | gun_stolen | gun_type | incident_characteristics | latitude | location_description | longitude | n_guns_involved | notes | participant_age | participant_age_group | participant_gender | participant_name | participant_relationship | participant_status | participant_type | sources | state_house_district | state_senate_district |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 658184 | 2016-09-18 | Texas | Pasadena | 5690 Fairmont Pkwy | 0 | 1 | http://www.gunviolencearchive.org/incident/658184 | http://www.khou.com/news/local/off-duty-pct-5-deputy-injured-in-pasadena-shooting/320641271 | False | 36.0 | 0::Unknown | 0::Unknown | Shot - Wounded/Injured\|\|Accidental Shooting\|\|Accidental Shooting - Injury\|\|Self-Inflicted (not suicide or suicide attempt - NO PERP)\|\|Officer Involved Incident\|\|Officer Involved Shooting - Officer shot | 29.6498 | Marshalls | -95.1549 | 1.0 | Deputy shoots at thief who was trying to run him over but the shot ricochets and hits deputy. |  | 0::Adult 18+\|\|1::Adult 18+ | 0::Male\|\|1::Male | 0::Deputy |  | 0::Injured\|\|1::Unharmed | 0::Victim\|\|1::Subject-Suspect | http://www.khou.com/news/local/off-duty-pct-5-deputy-injured-in-pasadena-shooting/320641271 | 128.0 | 11.0 |
| 959407 | 2017-10-11 | California | San Jose | 150 W Hedding St | 0 | 0 | http://www.gunviolencearchive.org/incident/959407 | http://www.mercurynews.com/2017/10/13/pat-down-schmat-down-inmate-smuggles-in-gun-via-jail-purse/ | False | 19.0 | 0::Unknown | 0::22 LR | Non-Shooting Incident\|\|Possession of gun by felon or prohibited person | 37.3513 | Santa Clara Jail | -121.907 | 1.0 | inmate smuggled gun illegally into jail |  | 0::Adult 18+ | 0::Female |  |  | 0::Unharmed, Arrested | 0::Subject-Suspect | http://www.mercurynews.com/2017/10/13/pat-down-schmat-down-inmate-smuggles-in-gun-via-jail-purse/ | 27.0 | 15.0 |
| 856979 | 2017-05-29 | Colorado | Montrose | 1308 E Main St | 0 | 1 | http://www.gunviolencearchive.org/incident/856979 | http://www.gjsentinel.com/news/articles/13yearold-boy-shot-while-sleeping-at-montrose-home | False | 3.0 | 0::Unknown | 0::Unknown | Shot - Wounded/Injured | 38.486 | Ikies Trailer Park | -107.867 | 1.0 |  | 0::13 | 0::Teen 12-17 | 0::Male |  |  | 0::Injured | 0::Victim | http://www.gjsentinel.com/news/articles/13yearold-boy-shot-while-sleeping-at-montrose-home | 58.0 | 6.0 |
| 692642 | 2016-11-04 | Illinois | Chicago | 3500 block of West Augusta Boulevard | 0 | 1 | http://www.gunviolencearchive.org/incident/692642 | http://chicago.suntimes.com/news/man-42-shot-in-humboldt-park/ | False | 7.0 | 0::Unknown | 0::Unknown | Shot - Wounded/Injured\|\|Drive-by (car to street, car to car) | 41.8991 | Humboldt Park | -87.714 | 1.0 | Car-to-car drive-by wounds driver, leg; | 0::42 | 0::Adult 18+ | 0::Male\|\|1::Male |  |  | 0::Injured\|\|1::Unharmed | 0::Victim\|\|1::Subject-Suspect | http://chicago.suntimes.com/news/man-42-shot-in-humboldt-park/ | 10.0 | 5.0 |
| 267884 | 2014-12-02 | Alabama | Birmingham | 1000 block of 15th Place SW | 0 | 1 | http://www.gunviolencearchive.org/incident/267884 | http://www.al.com/news/birmingham/index.ssf/2014/12/suspected_burglar_seriously_wo.html | False | 7.0 |  |  | Shot - Wounded/Injured\|\|Defensive Use\|\|Defensive Use - Victim stops crime | 33.4867 |  | -86.8553 |  |  |  |  | 0::Male |  |  | 0::Injured\|\|1::Unharmed | 0::Subject-Suspect\|\|1::Subject-Suspect | http://www.al.com/news/birmingham/index.ssf/2014/12/suspected_burglar_seriously_wo.html | 52.0 | 18.0 |


## Analysis by City: Chicago, IL
To aid for better visualizations, I decided to focus on certain cities rather than try to visualize shootings across the entire United States. For the next several sections, all data will be filtered towards Chicago, Illinois since that was the city with the most shootings in the dataset. 

```python
df_city = df_guns.loc[df_guns['city_or_county'].str.contains(city)]
df_city = df_city.loc[df_guns['state']==state]
df_city = df_city.loc[df_city['longitude'].notnull()]
```

The original python file can be downloaded [here]() which can allow users to change the city that analysis is performed on by modifying the <span style="font-family:Consolas; font-size:4em;">city</span> and <span style="font-family:Consolas; font-size:4em;">state</span> variables at the beginning of the script.

### KMeans Clustering for City Segmentation

```python
K = np.arange(21)[1:]
inertias = []
for k in K:
    kmeans = KMeans(n_clusters=k).fit(df_city[['latitude', 'longitude']])
    inertias.append(kmeans.inertia_)
```


