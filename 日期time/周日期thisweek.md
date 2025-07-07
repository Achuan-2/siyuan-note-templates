.action{$monday := now.AddDate 0 0 (int (sub 1 (int (now | Weekday))))}
.action{$sunday := now.AddDate 0 0 (int (sub 7 (int (now | Weekday))))}

.action{$monday | date "20060102"} ~ .action{$sunday | date "20060102"}