<h1> Data Manipulation Technics and Functions. </h1>

<br>

  
In this section we are going to cover the following.

<h2> Table of Content </h2>
<ul> 
      <li>Sorting DataFrame </li>
      <li>Merging DataFrame </li>


</ul>

 
 
 Before we get startted lets introduce the funtion that allows you to drop obervation with missing data. the <b> dropna() </b> funtion. In the parameter we supply the value (how="any"). Let us now import important packages and a dataset.
 
 
 
 <h3>Select a table based on a condition.</h3>
 
 In order to conditionally select column you might have write the following <b> df[df['arrival_date_year']==2] </b> .  Now to explain this. df means a dataframe and arrival_date_year indicates the name of the column and lastly ==2 indicates the condion of the column you want to select. translation of the code above means that in dataframe df you need to return records where the arrivala_date_year is equal to 2


```python
import pandas as pd
import numpy as np

data_set = pd.read_csv("D:\\hotel_bookings.csv")
New_data= data_set.dropna(how="any")
New_data.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>hotel</th>
      <th>is_canceled</th>
      <th>lead_time</th>
      <th>arrival_date_year</th>
      <th>arrival_date_month</th>
      <th>arrival_date_week_number</th>
      <th>arrival_date_day_of_month</th>
      <th>stays_in_weekend_nights</th>
      <th>stays_in_week_nights</th>
      <th>adults</th>
      <th>...</th>
      <th>deposit_type</th>
      <th>agent</th>
      <th>company</th>
      <th>days_in_waiting_list</th>
      <th>customer_type</th>
      <th>adr</th>
      <th>required_car_parking_spaces</th>
      <th>total_of_special_requests</th>
      <th>reservation_status</th>
      <th>reservation_status_date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2392</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>6</td>
      <td>2015</td>
      <td>October</td>
      <td>42</td>
      <td>11</td>
      <td>2</td>
      <td>0</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>240.0</td>
      <td>113.0</td>
      <td>0</td>
      <td>Transient</td>
      <td>82.0</td>
      <td>1</td>
      <td>1</td>
      <td>Check-Out</td>
      <td>2015-10-13</td>
    </tr>
    <tr>
      <th>2697</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>24</td>
      <td>2015</td>
      <td>October</td>
      <td>44</td>
      <td>26</td>
      <td>7</td>
      <td>15</td>
      <td>1</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>185.0</td>
      <td>281.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>52.2</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2015-11-17</td>
    </tr>
    <tr>
      <th>2867</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>24</td>
      <td>2015</td>
      <td>November</td>
      <td>45</td>
      <td>3</td>
      <td>0</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>334.0</td>
      <td>281.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>48.0</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2015-11-06</td>
    </tr>
    <tr>
      <th>2877</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>24</td>
      <td>2015</td>
      <td>November</td>
      <td>45</td>
      <td>3</td>
      <td>2</td>
      <td>10</td>
      <td>1</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>328.0</td>
      <td>281.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>40.0</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2015-11-15</td>
    </tr>
    <tr>
      <th>2878</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>24</td>
      <td>2015</td>
      <td>November</td>
      <td>45</td>
      <td>3</td>
      <td>3</td>
      <td>10</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>326.0</td>
      <td>281.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>48.0</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2015-11-16</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 32 columns</p>
</div>



<h1>1. Sorting DataFrame.</h1>

Pandas has two useful functions that are used to sort data frames
<ul> 
      <li> <b>Sort_value() </b> which is used to sort pandas dataframe by one column or morre columns. </li>
      <li> <b>sort_index() </b> which is used to sort pandas dataframe by row index</li>
</ul>

Each of these functions come with numerous optins, like sorting the dataframe in a specific order (ascending or descending), sorting in place, sorting with missing value and sorting by specific algorithm(you can define that algorithm)



<br>

<h4> Implimantation of sort values() function </h4>
    


Sort_values() function takes multiple options like:
<ul> 
      <li> <b>ascending </b> By default, sorting is in ascending order. when you pass the value false here, the dataframe will be sorted in descending order. </li>
      <li> <b>inplace</b> which is used to overwrite the original dataframe after sorting. if the value is true on the inplace method. after sorting of the dataframe the results will be sorted in the original dataframe.</li>
</ul>
    
In the following code we will use the dataset we imported into this environment and use it to sort dataframe according to columns.


```python
New_data.sort_values(by='lead_time',ascending=False)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>hotel</th>
      <th>is_canceled</th>
      <th>lead_time</th>
      <th>arrival_date_year</th>
      <th>arrival_date_month</th>
      <th>arrival_date_week_number</th>
      <th>arrival_date_day_of_month</th>
      <th>stays_in_weekend_nights</th>
      <th>stays_in_week_nights</th>
      <th>adults</th>
      <th>...</th>
      <th>deposit_type</th>
      <th>agent</th>
      <th>company</th>
      <th>days_in_waiting_list</th>
      <th>customer_type</th>
      <th>adr</th>
      <th>required_car_parking_spaces</th>
      <th>total_of_special_requests</th>
      <th>reservation_status</th>
      <th>reservation_status_date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8762</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>364</td>
      <td>2016</td>
      <td>October</td>
      <td>42</td>
      <td>12</td>
      <td>1</td>
      <td>4</td>
      <td>3</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>223.0</td>
      <td>223.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>101.00</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-17</td>
    </tr>
    <tr>
      <th>99993</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99998</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99997</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99999</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>41005</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>0</td>
      <td>2015</td>
      <td>August</td>
      <td>33</td>
      <td>10</td>
      <td>1</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>0</td>
      <td>Transient</td>
      <td>115.00</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2015-08-14</td>
    </tr>
    <tr>
      <th>24278</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>0</td>
      <td>2016</td>
      <td>May</td>
      <td>21</td>
      <td>15</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>...</td>
      <td>Refundable</td>
      <td>405.0</td>
      <td>405.0</td>
      <td>0</td>
      <td>Group</td>
      <td>70.00</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-05-16</td>
    </tr>
    <tr>
      <th>41142</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>0</td>
      <td>2015</td>
      <td>August</td>
      <td>33</td>
      <td>13</td>
      <td>0</td>
      <td>2</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>0</td>
      <td>Transient</td>
      <td>85.00</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2015-08-15</td>
    </tr>
    <tr>
      <th>18855</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>0</td>
      <td>2015</td>
      <td>November</td>
      <td>49</td>
      <td>30</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>240.0</td>
      <td>331.0</td>
      <td>0</td>
      <td>Transient</td>
      <td>48.00</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2015-12-02</td>
    </tr>
    <tr>
      <th>41144</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>0</td>
      <td>2015</td>
      <td>August</td>
      <td>33</td>
      <td>13</td>
      <td>0</td>
      <td>2</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>9.0</td>
      <td>0</td>
      <td>Transient</td>
      <td>85.00</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2015-08-15</td>
    </tr>
  </tbody>
</table>
<p>217 rows × 32 columns</p>
</div>



Sometimes you might want to sort a dataframe based on the values of multiple columns. We can specify the columns we want to sort by as a list in the argument for sort_values() .<br>
e.g dataframe.sort_values(by=[column1, column2]). Lets impliment this in a code then observe what happens.<br>
<b> Note. </b> when yo pass more than one column in the argument. python will first sort the Values of the first columns then followed by the values of the second columns.



```python
New_data.sort_values(by=['lead_time','arrival_date_week_number','arrival_date_month'])
New_data.iloc[:10]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>hotel</th>
      <th>is_canceled</th>
      <th>lead_time</th>
      <th>arrival_date_year</th>
      <th>arrival_date_month</th>
      <th>arrival_date_week_number</th>
      <th>arrival_date_day_of_month</th>
      <th>stays_in_weekend_nights</th>
      <th>stays_in_week_nights</th>
      <th>adults</th>
      <th>...</th>
      <th>deposit_type</th>
      <th>agent</th>
      <th>company</th>
      <th>days_in_waiting_list</th>
      <th>customer_type</th>
      <th>adr</th>
      <th>required_car_parking_spaces</th>
      <th>total_of_special_requests</th>
      <th>reservation_status</th>
      <th>reservation_status_date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8762</th>
      <td>Resort Hotel</td>
      <td>0</td>
      <td>364</td>
      <td>2016</td>
      <td>October</td>
      <td>42</td>
      <td>12</td>
      <td>1</td>
      <td>4</td>
      <td>3</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>223.0</td>
      <td>223.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>101.00</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-17</td>
    </tr>
    <tr>
      <th>99976</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99952</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99964</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99966</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99946</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99993</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99999</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99997</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
    <tr>
      <th>99998</th>
      <td>City Hotel</td>
      <td>0</td>
      <td>256</td>
      <td>2016</td>
      <td>October</td>
      <td>43</td>
      <td>16</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>...</td>
      <td>No Deposit</td>
      <td>9.0</td>
      <td>333.0</td>
      <td>0</td>
      <td>Transient-Party</td>
      <td>100.75</td>
      <td>0</td>
      <td>0</td>
      <td>Check-Out</td>
      <td>2016-10-21</td>
    </tr>
  </tbody>
</table>
<p>10 rows × 32 columns</p>
</div>



<h4> Implimantation of sort_index() function </h4>
We use sort_index to sort pandas by row index.. We can use row index with inplace = True to retrieve the original data frame after sorting it.


```python
Original_data = New_data.sort_index(inplace = True)
#no changes may be seen in this code here as the New_data is a subset of the original data. in this case the inplace function fails
```

<h1> Merging and joining of dataframes </h1>

Joining and merging dataframe is the core process to start with data analysis and machine learning tasks.<br>
It is one of the most important toolkit which every data analyst or data scientist should master because in most if not all cases data comes from multiple sources and file sources.

<b>Pandas has two useful functions for merging dataframes. </b>

<ul>  
    <li> <b>Concat()</b> Is used to apped dataFrames one below the other or side ways. </li>
    <li> <b> Merge() </b> Is used to combine data on the basis of common column, most of the cases it is a key</li>
</ul>

The following code creates two or three dummy dataFrames so we ca apply the two functions on them.




```python
df1 = pd.DataFrame({ 'A' : ['A1','A2','A3','A4'],
                      'B' : ['B1','B2','B3','B4'],
                      'C' : ['C1','C2','C3','C4']
}, index = [0,1,2,4])

df2 = pd.DataFrame({ 'A' : ['A4','A5','A6','A7'],
                      'B' : ['B4','B5','B6','B7'],
                      'C' : ['C4','C5','C6','C7']
}, index = [5,6,7,8])

df3 = pd.DataFrame({ 'A' : ['A8','A9','A10','A11'],
                      'B' : ['B8','B9','B10','B11'],
                      'C' : ['C8','C9','C10','C11']
}, index = [9,10,11,12])


```

The following code is just an implimentation of concat function and it combines two dataframe one below the other,


```python
result = pd.concat([df1,df2])
result
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A1</td>
      <td>B1</td>
      <td>C1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A2</td>
      <td>B2</td>
      <td>C2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>A3</td>
      <td>B3</td>
      <td>C3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>A4</td>
      <td>B4</td>
      <td>C4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>A4</td>
      <td>B4</td>
      <td>C4</td>
    </tr>
    <tr>
      <th>6</th>
      <td>A5</td>
      <td>B5</td>
      <td>C5</td>
    </tr>
    <tr>
      <th>7</th>
      <td>A6</td>
      <td>B6</td>
      <td>C6</td>
    </tr>
    <tr>
      <th>8</th>
      <td>A7</td>
      <td>B7</td>
      <td>C7</td>
    </tr>
  </tbody>
</table>
</div>



Pandas also provides you with an option to lable your data with a key value so that you can know which dataa comes from which dataframe. You achive this by passing an additional argument(key) into pd.concat() function, spcifiying names of DataFrames in a list. We demonstrate this in the following code.


```python
result = pd.concat([df1,df2, df3], keys = ['x','y','z']) 
#in this case the key representations of data frames are as follows. x =df1, y=df2, and x= df3
result
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="4" valign="top">x</th>
      <th>0</th>
      <td>A1</td>
      <td>B1</td>
      <td>C1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A2</td>
      <td>B2</td>
      <td>C2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>A3</td>
      <td>B3</td>
      <td>C3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>A4</td>
      <td>B4</td>
      <td>C4</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">y</th>
      <th>5</th>
      <td>A4</td>
      <td>B4</td>
      <td>C4</td>
    </tr>
    <tr>
      <th>6</th>
      <td>A5</td>
      <td>B5</td>
      <td>C5</td>
    </tr>
    <tr>
      <th>7</th>
      <td>A6</td>
      <td>B6</td>
      <td>C6</td>
    </tr>
    <tr>
      <th>8</th>
      <td>A7</td>
      <td>B7</td>
      <td>C7</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">z</th>
      <th>9</th>
      <td>A8</td>
      <td>B8</td>
      <td>C8</td>
    </tr>
    <tr>
      <th>10</th>
      <td>A9</td>
      <td>B9</td>
      <td>C9</td>
    </tr>
    <tr>
      <th>11</th>
      <td>A10</td>
      <td>B10</td>
      <td>C10</td>
    </tr>
    <tr>
      <th>12</th>
      <td>A11</td>
      <td>B11</td>
      <td>C11</td>
    </tr>
  </tbody>
</table>
</div>


