……日记模板内容……



.action{ $weekday := now | date "Mon" }

.action{$docIconDict := dict "Mon" "day_Today_1_Monday.png" "Tue" "day_Today_2_Tuesday.png" "Wed" "day_Today_3_Wednesday.png" "Thu" "day_Today_4_Thursday.png" "Fri" "day_Today_5_Friday.png" "Sat" "day_Today_6_Saturday.png" "Sun" "day_Today_7_Sunday.png"} 
.action{$docIconUrl := get $docIconDict $weekday}


{: icon="time/.action{$docIconUrl}"   type="doc"}