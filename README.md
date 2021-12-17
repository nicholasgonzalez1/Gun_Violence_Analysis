# Gun Violence in the U.S.
<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#inspiration-for-the-project">Inspiration for the Project</a></li>
    <li><a href="#built-with">Built With</a></li>
    <li><a href="#getting-started">Getting Started</a></li>
    <li>
      <a href="#analysis-by-city-chicago-il">Analysis by City: Chicago, IL</a>
      <ul>
        <li><a href="#kmeans-clustering-for-city-segmentation">KMeans Clustering for City Segmentation</a></li>
        <li><a href="#cleaning-incident-characteristics-fields">Cleaning Incident Characteristics Fields</a></li>
        <li><a href="#folium-map-visualization">Folium Map Visualization</a></li>
      </ul>
    </li>
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
# Filter on incidents whose city or county contains "Chicago"
df_city = df_guns.loc[df_guns['city_or_county'].str.contains(city)]

# Filter for all results from previous statement to ensure in the state of Illinois
df_city = df_city.loc[df_guns['state']==state]

# Filter out any instances where geospatial data is not available
df_city = df_city.loc[df_city['longitude'].notnull()]
```

The original python file can be downloaded [here]() which can allow users to change the city that analysis is performed on by modifying the <span style="font-family:Consolas; font-size:4em;">city</span> and <span style="font-family:Consolas; font-size:4em;">state</span> variables at the beginning of the script.

### KMeans Clustering for City Segmentation

Below, I ran a KMeans algorithm in order segment the shootings within the city. We'll use the elbow method to determine what is the optimal number of clusters to use when plotting our gun incidents. The elbow graph displayed below shows how the within-cluster sum-of-squares (WCSS) decreases for each additional cluster added.

```python
# Test cluster amounts 1 - 20
K = np.arange(21)[1:]

# Run KMeans algorithm for each number of clusters and record its within-cluster sum-of-squares
inertias = []
for k in K:
    kmeans = KMeans(n_clusters=k).fit(df_city[['latitude', 'longitude']])
    inertias.append(kmeans.inertia_)
```
<br>
<figure>
  <p align="center">
    <kbd>
      <img src="https://github.com/nicholasgonzalez1/Gun_Violence_Analysis/blob/main/images/elbow_graph.jpg?raw=true" width="550">
    </kbd>
  </p>
</figure>

The code snippet below determines the optimal number of clusters. We select the first cluster amount which has a percent decrease less than 10% from the initial within-cluster sum-of-squares amount for k=1. The 10% value is stored in the variable <span style="font-family:Consolas; font-size:4em;">pct_change</span> and serves as the pre-specified threshold. This value can be adjusted according to user preferences.

```python
inertias = np.array(inertias)
start = inertias[0]

# Statement below calculates percent decrease in WCSS for each additional cluster
inertias = -100 * np.diff((inertias[1:] - np.repeat(start, len(inertias[1:])))/np.repeat(start, len(inertias[1:])))

# Select the first number of clusters which is less than a pre-specified threshold pct_change
n_clusters = np.argwhere(inertias < pct_change)[0][0]
n_clusters = n_clusters + 3  # A value of 3 is added to account for index changes in NumPy functions
```

### Cleaning Incident Characteristics Fields

One of the objectives when creating this visualization includes providing different weights according to the severity of the shooting. For example, it should be apparent when looking at the map which shooting was more deadly when comparing two separate incidents. In order to achieve this, the fields 'n_injured', 'n_killed', and 'participant_type' will need to be further scrubbed. The code snippet below creates a Pandas data frame containing only the columns of interest for creating our visualization.

```python
# Run KMeans for previously calculated number of clusters and convert cluster assignments to Pandas column
kmeans = KMeans(n_clusters=n_clusters).fit(df_city[['longitude', 'latitude']])
cluster_assignments = pd.DataFrame({'cluster_assignment': list(kmeans.labels_)})

# Extract columns that will be used or need to be cleaned, and concat cluster assignments
df_plot = df_city[['latitude', 'longitude', 'n_injured', 'n_killed', 'participant_type']].reset_index(drop=True)
df_plot = pd.concat([df_plot, cluster_assignments], axis=1)
```
#### Assign a Deadliness Factor

In order to differentiate how deadly an incident was, the opaqueness of the plotted datapoints will be adjusted according to how many incident participants were injured or killed. The table below provides a breakdown of this metric for only Chicago, IL.
<br>
<figure>
  <p align="center">
    <kbd>
      <img src="https://github.com/nicholasgonzalez1/Gun_Violence_Analysis/blob/main/images/chicago_breakdown.png?raw=true" width="200">
    </kbd>
  </p>
</figure>

The defined function below takes in two arguments, the number of participants injured and killed, and assigns a deadliness factor according to the breakdown table above. These values will be used directly to adjust the opaqueness of datapoints in the final visualization.

```python
def assign_deadliness(n_injured, n_killed):
    if (n_injured <= 2) and (n_killed == 0):
        return 0.05
    elif (n_injured > 2) and (n_killed == 0):
        return 0.10
    elif (n_injured == 0) and (n_killed == 1):
        return 0.35
    elif (n_injured > 0) and (n_killed == 1):
        return 0.40
    elif (n_killed > 1):
        return 0.50
    else:
        return 0.05
```

```python
df_plot['deadliness_factor'] = df_plot.apply(lambda x: assign_deadliness(x['n_injured'], x['n_killed']), axis=1)
```
#### Assign a Shooting Size

Similar to differentiating incidents based on deadliness, the size (i.e. number of participants identified in an incident) was also considered. For example, a shooting with 5 individuals identified, regardless of whether they were victims or suspects, would carry more size than an incident with only 1 participant identified.

The function below takes in values from the 'participant_type' field and returns a dictionary object. Each item in the dictionary corresponds to how many victims and suspects were involved in the gun incident. An demo is provided below the clean_participants_type() function displaying what an example output would look like. 

```python
def clean_participants_type(row_value):

    # logic below produces a Pandas series object listing whether each participant was a victim or suspect
    if row_value is np.NaN:
        return {'Victim':0, 'Subject-Suspect':0}    
    elif '::' in row_value:
        types = pd.Series([person.split('::')[1] for person in row_value.split('||')])
    else:
        types = pd.Series([person.split(':')[1] for person in row_value.split('|')])
        
    # using value_counts(), the total number of victims and suspects is determined, which is then converted to a dictionary
    types = dict(types.value_counts())
    
    # logic below ensures that if incident has no victims or suspects, respective keys are still included
    if 'Victim' not in types.keys():
        types['Victim'] = 0
    if 'Subject-Suspect' not in types.keys():
        types['Subject-Suspect'] = 0
    
    return types
```

```python
""" --- Demo of clean_participants_type() --- """
test_value = '0::Victim||1::Victim||2::Victim||3::Victim||4::Subject-Suspect'
participants = clean_participants_type(test_value)
participants['Victim']          # outputs 4
participants['Subject-Suspect'] # outputs 1
```

Using this function, two columns are created containing the number of suspects and victims for a given incident. A third column was constructed containing the sum of the previous two columns, 'n_participants'.

```python
df_plot['n_victims'] = df_plot.apply(lambda x: clean_participants_type(x['participant_type'])['Victim'], axis=1)
df_plot['n_suspects'] = df_plot.apply(lambda x: clean_participants_type(x['participant_type'])['Subject-Suspect'], axis=1)
df_plot['n_participants'] = df_plot['n_victims'] + df_plot['n_suspects']
```
Similar to assinging a deadliness factor, another function was created in order to assign weights corresponding to the incident size.

```python
def assign_shooting_size(size):
    if size <= 1:
        return 200
    elif size <= 3:
        return 250
    elif size > 3:
        return 400
    else:
        return 200
```
```python
df_plot['shooting_size_weight'] = df_plot.apply(lambda x: assign_shooting_size(x['n_participants']), axis=1)
```

### Folium Map Visualization
