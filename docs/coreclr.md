# grep/awk/sed命令学习
  ```
  grep "<test " ./*.xml | sed 's/.*name="\([^"]*\)".*type="\([^"]*\)".*result="\([^"]*\)".*/\1,\2,\3/' 
  ```
  ```
  grep "Time:" artifacts/log/Debug/*.log | awk 'BEGIN{printf "%-50s\tTotal\tPassed\tErrors\tFailed\tSkipped\tTime\tLog\n","TestName"} {total+=$4;errors+=$6;failed+=$8;skipped+=$10;time+=$12; printf "%-50s\t%d\t%d\t%d\t%d\t%d\t%.2f\t%s\n",$2,$4,$4-$6-$8-$10,$6,$8,$10,$12,$1} END{printf "%-50s\t%d\t%d\t%d\t%d\t%d\t%.2f\t%s\n","Summary",total,total-errors-failed-skipped,errors,failed,skipped,time,""}' | tee summary.log
  ```

查找引号之间的字符串
\转义符

