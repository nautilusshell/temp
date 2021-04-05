# postgresql批量插入数据
```
insert into inference_time_statistics (service_name, project_label, task_label, inference_duration, inference_time) 
select 'test', 'projectLabel', 'taskLabel', trunc(random() * 100 + 1), (extract(epoch FROM date_trunc('day', current_timestamp)) - trunc(random() * 100 + 1))
FROM generate_series(1,1000000) ;

delete from inference_time_statistics where service_name='test'; 


export DLWS_LAUNCH_CMD="cp -r /data/code/SSD_MobileNet_FPN_for_MindSpore /tmp/apprun && cd /tmp/apprun && chmod -R a+w . && python /data/code/SSD_MobileNet_FPN_for_MindSpore/train.py --train_dataset_path=/data/dataset-images/dataset-manager/storage/add2c2f7-27fd-41eb-acd3-f88dd0c9253c --output_dir=/home/_output --classes=\"dog,cat,people\" --input_width=2048  --input_height=1536 --batch_size=2 --epoch_size=100 --init_lr=0.001;sleep 86400"
```
