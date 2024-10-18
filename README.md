# Weather-Prediction-Project

Create database Weather_prediction_project;
use Weather_prediction_project;

select * from w_dataset;

-- Display the data for rainy weather 
select * 
from w_dataset
where weather= "rain";

-- Provide row number to the data 
select row_number() over (order by weather) as ID_no
from w_dataset;

-- Show the data which has total humid and group the data by weather 
select sum(humid)
from w_dataset
group by weather;

-- split the data using weather
select *,ntile(5) over (order by Weather) as data 
from w_dataset;
