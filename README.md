# dw-starter
This is sample project for [Bloods](https://www.rocy-data.com/products/bigdata/bloods-dwdi-core).  
`Bloods` is zero-code big data and science framework by parsing XML data flow to Spark big data or data mining and intelligence code can run at cluster. It lets big data calculation simpler and clear.
## Install
1. Download the binary from [here](https://www.rocy-data.com/downloads#bloods-dwdi-core) and decompress it to some directory,we name it as `${ROCY_DATA_HOME}`, this directory has the following content.
*  `Bloods` product,its name format: `bloods-1.0.0`
* `license`,it is free in public test period.
* `bloods-1.0.0/actions` has action extensions,relative to [Bloods IOV](https://www.rocy-data.com/docs/bloods_iov/#install) ,<strong>HAVE NO</strong> IOV extensions: `iov-bigdata-dw-1.0.0.jar` and `iov-bigdata-di-1.0.0.jar`
2. You can visit [Office Site](https://www.rocy-data.com) and register to get free license file(login->My Account->Licenses->Get License), save this file to `${ROCY_DATA_HOME}`
3. Start `Bloods`
```bash
cd ${ROCY_DATA_HOME}
bash ${ROCY_DATA_HOME}/bloods-1.0.0/bin/start-bloods-dwdi-core.sh
```
You can enter following command to know what commands are supported
```shell
help
```
also, can reference online docs: [Bloods Console](https://www.rocy-data.com/docs/bloods_console).
4. You also can enjoin [SaaS](https://www.rocy-data.com/nervous/face) ,it is simple but local installation has more features.

## Samples
Their installed location is  `${ROCY_DATA_HOME}/bloods-1.0.0/dw-starter/samples`,same to this project which have 4 samples
1. dw_samples
   dw is for common calculations
2. di_samples
   di is for data mining or data intelligence,includes features of dw
3. iov_dw_samples
   iov_dw is common calculations but add some actions for vertical and special domain IOV  
   Tip: [Bloods IOV](https://www.rocy-data.com/docs/bloods_iov) can execute these samples
4. iov_di_samples
   for data mining or data intelligence but add some actions for vertical and special domain IOV  
   Tip: [Bloods IOV](https://www.rocy-data.com/docs/bloods_iov) can execute these samples

Now we have`dw_samples` as sample to show how to execute them
* First start`Bloods`
```shell
cd ${ROCY_DATA_HOME}/bloods-1.0.0/bin
./start-bloods-dwdi-core.sh
```
Afterwards,enter into `Bloods Console`,following command can come in sample directory
```shell
cd ../dw-starter/samples/dw_samples
```
* Execute
  You can execute `sources`,`transforms`,`sinks` to view existent `actions`,for example `sinks`
```shell
sinks
```
Output is:
```shell
id_sink_plugin[/dw/plugin/sink.xml]                                             id_sink_range_date_quarter[/dw/range_date/range_date_ref.xml]               
id_sink_range_date_sink_quarter[/dw/range_date/range_date_ref.xml]              id_sink_schedule[/dw/scheduler/schedule.xml]                                
id_sink_schedule_month_day1[/dw/scheduler/schedule.xml]                         id_sink_schedule_month_end[/dw/scheduler/schedule.xml]                      
id_sink_schedule_weekly[/dw/scheduler/schedule.xml]                             id_sink_schedule_year1[/dw/scheduler/schedule.xml]                          
id_sink_schedule_year2[/dw/scheduler/schedule.xml]                              id_word_count_stat_sink[/dw/hello_world.xml]
```
Execute someone task:
```shell
run -t id_sink_plugin
```
Also, can execute all tasks:
```shell
debug_all
```
Finally,can execute following command to deploy to cluster,it generates spark-submit script to run at cluster.
```shell
deploy
```
More deeply,we can review XML configuration with zero-code in other directory (di_samples/iov_dw_samples/iov_di_samples)) to understand it.

