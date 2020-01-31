# Eva

1.
select start_station_name,end_station_name
from `bigquery-public-data.austin_bikeshare.bikeshare_trips`
where start_station_name="Pease Park"
order by start_station_name asc
limit 10	   

Row	f0_	
1	
29.032961731747758


2.
select long_description,	is_header_code
from `bigquery-public-data.cms_codes.icd10_diagnoses_2019`
limit 6

Row	long_description	is_header_code	
1	
Cholera, unspecified
false
2	
Malignant melanoma of other parts of face
false
3	
Thrombocytopenia, unspecified
false
4	
Drug or chemical induced diabetes mellitus with proliferative diabetic retinopathy without macular edema, bilateral
false
5	
Cannabis abuse with intoxication, unspecified
false
6	
Generalized idiopathic epilepsy and epileptic syndromes, not intractable, without status epilepticus
false


	 
3.
select year,gender,name
from `bigquery-public-data.usa_names.usa_1910_current`
where gender= "M" and name="Ryan" and year=1971
order by name desc
limit 7
	
  year	gender	name
1971	M	Ryan
1971	M	Ryan
1971	M	Ryan
1971	M	Ryan
1971	M	Ryan
1971	M	Ryan
1971	M	Ryan


4.
select year,country_code,gross_reproduction_rate	sex_ratio_at_birth
from `bigquery-public-data.census_bureau_international.age_specific_fertility_rates`
where sex_ratio_at_birth > 2
order by country_code


5.
select country_name,year,sex,population,age
from `bigquery-public-data.census_bureau_international.midyear_population_agespecific`
where age > 60 and sex="Female"
limit 6	 

country_name	year	sex	population	age
Nauru	2001	Female	10	61
Nauru	2001	Female	11	62
Nauru	2001	Female	9	63
Nauru	2001	Female	8	64
Nauru	2001	Female	9	65
Nauru	2001	Female	7	66


6.
select education,occupation,race,sex,hours_per_week,income_bracket
from `bigquery-public-data.ml_datasets.census_adult_income`
where race=" Black" and hours_per_week < 34 
limit 6	 

education	occupation	race	sex	hours_per_week	income_bracket
" 9th"	" Priv-house-serv"	" Black"	" Female"	10	" <=50K"
" 9th"	" Other-service"	" Black"	" Female"	24	" <=50K"
" 10th"	" Other-service"	" Black"	" Female"	32	" <=50K"
" 11th"	" Other-service"	" Black"	" Female"	30	" <=50K"
" 5th-6th"	" Priv-house-serv"	" Black"	" Female"	10	" <=50K"
" HS-grad"	" ?"	" Black"	" Female"	30	" <=50K"

7.
select max(age), min(age)
from `bigquery-public-data.census_bureau_international.midyear_population_agespecific`

f0_	f1_
100	0
	 
8.
select avg(age)
from `bigquery-public-data.census_bureau_international.midyear_population_agespecific`	 

f0_
50.000000000001

	 
   
9. select austin.unique_key, request. complaint_type
from `bigquery-public-data.austin_311.311_service_requests` as request
left join `bigquery-public-data.austin_311.311_request`as austin
on (request.unique_key = austin.unique_key)

ow	unique_key	complaint_type	
1	
14-00097246
ACDEADBI
2	
null
ACLONAG
3	
null
ACLONAG
4	
16-00241246
ACLONAG
5	
19-00006042
ACLONAG
6	
16-00287114
ACLONAG
7	
null
ACLONAG

10.
select avg(duration_minutes) 
from `bigquery-public-data.austin_bikeshare.bikeshare_trips`
f0_
29.032961731747758

	 

