主要的流程。

1、ldb_make_room_for_write 
   给写入准备空间
   进入循环：
   1）要是允许延迟写入，L0文件超过LDB_L0_SLOWDOWN_WRITES_TRIGGER，睡1ms
   2）要是memtable还有空间，马上返回。
   最后会调用ldb_maybe_schedule_compaction

2、ldb_maybe_schedule_compaction
   是否需要加入计划compact任务
   
