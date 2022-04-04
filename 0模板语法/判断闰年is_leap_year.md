
.action{$this_year :=2019}
.action{/* 判断闰年，相当于if year % 4 == 0 and year % 100 != 0 or year % 400 == 0 */}

.action{$is_leap := any (all (empty (mod $this_year  4)) (not (empty (mod $this_year  100)))) (empty (mod $this_year  400))}
.action{$MonthDict1 := dict "1" "31" "2" "28" "3" "31" "4" "30" "5" "31" "6" "30" "7" "31" "8" "31" "9" "30" "10" "31" "11" "30" "12" "31"}
.action{$MonthDict2 := dict "1" "31" "2" "29" "3" "31" "4" "30" "5" "31" "6" "30" "7" "31" "8" "31" "9" "30" "10" "31" "11" "30" "12" "31"}
.action{$Dicts := dict "true" $MonthDict2 "false" $MonthDict1}
.action{$MonthDict := get $Dicts (toString $is_leap)}
.action{$MonthDict}