This API can monitor the cpu consumption of the workers by using Anypoint Cloudhub API and increase/decrease the number of the workers with a given threshold value.

get /dashboardStats
This operation gets worker statistic information of the specified api (application_name).

put /scaleControl
This operation increases or decreases the number of the workers with the threshold value (set_threshold) and changes the worker size (worker_size).
If the average of the cpu consumption is higher than the threshold value, it will add one worker and if the average of the cpu consumption is lower than the threshold value, it will shutdown one worker.

The threshold value is specified as a number between 3 - 95.

scheduler
This API can be scheduled and monitor the cpu consumption, compare with the default threshold value and increase or decrease the number of the workers. 

The default value for the scheduler is currently set to 10 minutes and the theshold value is set to 3.

It is recommended to increase the threshold value to something more meaningful that represents the average CPU% utilisation of all the Mule workers for your application that you would like to scale.

For example:
If my Mule Application is running on 1 vCore and 2 workers and the average CPU utilisation is greater than 50% then add another worker. 
For this example set the threshold to 50.
