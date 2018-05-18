This file contains some quick information about some of the specifics of the
different cities, household income per district dataset. Obviously the data
was not always in the same format for every city, so sometimes we had to do
some post processing.

How do we fill up empty districts in a specific year?
If for a certain year there is not data available for a specific district we do
the following:
  1. If the district has data for the year before and after we linearly interpolate.
  2. If we do not have data for a specific year at the very beginning or at the end
     of the available data set, i.e. if for the current year there is either
     no data for the previous year(but data for the next year) or no data for
     the next year(but data for the previous year) we set that years household
     income to the income of its neighbor. That means if there is no data
     for the previous year we set it to the income of the next year. If there
     is not data for the next year we set it to the income of the previous year.

     The advantage of this is that we do not assume anything about the missing data.
     What we are actually interested in are changes in the household income and if these
     correlate with the smartness of the city. So the reasonable thing to assume for
     missing data is that it did not change over a specific timeframe.

     Also note that this 2. case can only happen if the data set is missing some entries. We mark
     these with green in the database.

Smart cities 
###########################################


# Hamburg
#############
1. Some districts don't have any numbers for certain years. We use method
discribed in the beginning to fill up.
The districts are the following:
  - Hafencity (2004)
  - Sternschanze (2004)
  - Neuallermöhe (2004)

2. In 2010  nord-, mitte, and -süd Hamm became Hamm. So from 2007 - 2010 we just
averaged over the three districts that became Hamm in the end.

# Sydney
#############
We have an median weekly income. Thus to get a yearly income we multiplied times 52.
Some districts did not have enough people living there, thus there was no data
available for most years. We removed these districts, they are the following:
- 2129
- 2139
- 2006
Also for some specific years there was no data. We filled that up with the
usual approach mentioned in the beginning.

# Melbourne
#############
We have an median weekly income. Thus to get a yearly income we multiplied times 52.
Some districts did not have enough people living there, thus there was no data
available for most years. We removed these districts, they are the following:
- 3050
- 3045
- 3062
Also for some specific years there was no data. We filled that up with the
usual approach mentioned in the beginning.

# Berlin
#############
(average) We have monthly income. We multiply by 12 to get yearly income.

# New York
############# 
(Mean) Nothing special to mention.

# Vienna
#############
(Average)Nothing special to mention.

# Chicago
#############
(Mean) Nothing special to mention. 

# Los Angeles
#############
(Mean) We took all the postal codes form the city. Some postal codes thought, had no data at all or not enough. They are the following: 
- 90071
- 90073
- 90079
- 90090
- 90095

Some special years for some districts were just missing data. For these we applied the usual method and marked them green. 

# Boston 
##############
(Mean) We took postal codes from within the city. For some postalcodes too much data is missing. That leaves us with only one year of data so we removed those postal codes, these are the following: 
- 2446
- 2445
- 2203
- 2149

# Washington D.C
###################
(Mean) We had no or not enough data on the following districts. 
20045
20052
20053
20057
20064
20202
20204
20228
20230
20240
20245
20260
20307
20319
20373
20390
20405
20418
20427
20506
20510
20520
20535
20540
20551
20553
20560
20565
20566
20593

# San Francisco 
################
(Mean)Nothing special to mention. 

# London 
###############

Non-Smart cities
######################################

# San Antonio
################
(Mean). Not enough data and thus removed was the following postal code: 
- 78243

# San Diego
################
(Mean). Not enough data and thus removed were the following postal codes:
- 92147
- 92140
- 92135
- 92134
- 92132
- 92140

# Austin(Texas)
################
(mean). Not enough data and thus removed were the following postal codes:
- 78712

# Jacksonville
################
(mean). Not enough data and thus removed were the following postal codes:
- 32228

# San Juan (Puerto Rico)
#################
(mean). not enough data and thus removed were the following postal codes:
- 936
- 960

Postal code 906 was missing some data and thus we completed it in the usual way and marked it green. 

# Columbus
################
One datapoint missing and was filled up with usual method. 

# Indianapolis
###################
(mean). not enough data and thus removed were the following postal codes:
- 46183

# Brisbane
##################
(Median). No data found for following postal codes:
- 4189
- 4009
Data missing for one year for postal code 4072, filled up in usual manner.
We have an median weekly income. Thus to get a yearly income we multiplied times 52. 

# Perth
#################
We have an median weekly income. Thus to get a yearly income we multiplied times 52. 
We deleted postal code 6106 because it had a strange behaviour. In 2006 and 2011 median household income was 4500 but in 2016 it was 0, although people lived there. So either the statistical bureau made an error or maybe they are not earning anything anymore(which does not make much sense). Without wanting to imply anything we removed this postal code. 

# Adelaide
##########
We have an median weekly income. Thus to get a yearly income we multiplied times 52.
We deleted following postal codes because of not enought data: 
-5950
-5005