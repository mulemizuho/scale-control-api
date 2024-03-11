## Scale Control API

### Description
This Mule application can monitor the CPU consumption of all your application's workers and increase/decrease the number of the workers with a given threshold value (equal to avg CPU %) by using the Anypoint Cloudhub API.


## How to use it
**get /dashboardStats** \
This operation gets worker statistic information of the specified api (application_name).
\
\
**put /scaleControl** \
This operation increases or decreases the number of the workers with the threshold value (set_threshold) and changes the worker size (worker_size).
If the average of the cpu consumption is higher than the threshold value, it will add one worker and if the average of the cpu consumption is lower than the threshold value, it will shutdown one worker.

The threshold value is specified as a number between 3 - 95.
\
\
**scheduler** \
This API can be scheduled and monitor the cpu consumption, compare with the default threshold value and increase or decrease the number of the workers. 

The default value for the scheduler is currently set to 10 minutes and the theshold value is set to 3.

It is recommended to increase the threshold value to something more meaningful that represents the average CPU% utilisation of all the Mule workers for your application that you would like to scale.
\
\
**For example:** \
If your Mule Application is running on 1 vCore and 2 workers and the average CPU utilisation is greater than 50% then add another worker. 
This requires the threshold to be set to 50.

\
\
\
Disclaimer:
This is for demonstration purposes only. 
For production requirements, please consider using CloudHub's Autoscaling Features: https://docs.mulesoft.com/cloudhub/autoscaling-in-cloudhub
