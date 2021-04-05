# postgresql批量插入数据
```
insert into inference_time_statistics (service_name, project_label, task_label, inference_duration, inference_time) 
select 'test', 'projectLabel', 'taskLabel', trunc(random() * 100 + 1), (extract(epoch FROM date_trunc('day', current_timestamp)) - trunc(random() * 100 + 1))
FROM generate_series(1,1000000) ;
```
