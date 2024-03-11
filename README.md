This API can monitor the cpu consumption of the workers by using Anypoint Cloudhub API and increase/decrease the number of the workers with the threshold value.

get /dashboardStats
This operation gets worker statistic information of the specified api (application_name).

put /scaleControl
This operation increases or decreases the number of the workers with the threshold value (set_threshold) and changes the worker size (worker_size).
If the average of the cpu consumption is higher than the threshold value, it will add one worker and if the average of the cpu consumption is lower than the threshold value, it will shutdown one worker.

scheduler
This API can be scheduled and monitor the cpu consumption, compare with the default threshold value and increase or decrease the number of the workers. 
