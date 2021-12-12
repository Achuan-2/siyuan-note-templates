.action{$ini_date := "2022-01-01"}
.action{$countdown := (div ((toDate "2006-01-02" $ini_date).Sub now).Hours 24)}
距离2022年还有 .action{$countdown} 天