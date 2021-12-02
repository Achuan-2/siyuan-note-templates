.action{/* 尤克里里学习log */}
.action{$before := (div (now.Sub (toDate "2006-01-02" "2021-11-04")).Hours 24)}
## .action{ now | date "2006.01.02"} Day.action{$before} ？