.action{/*输出大纲*/}

.action{/*获取文档的基本信息*/}
.action{$notebox :=" "}
.action{$rootid:=.id}

.action{$tab:="  "}
.action{$firstIntType:=0}
.action{$firstHeadID:=" "}
.action{$getDocInfo:= (queryBlocks "SELECT * FROM blocks WHERE root_id='?' AND type= 'h'  limit 1" $rootid)}
.action{range $v:= $getDocInfo}
	.action{$Htype:=$v.SubType | replace "h" ""}
	.action{$firstIntType = $Htype | atoi}
.action{end}



.action{$blocks:= (queryBlocks "SELECT * FROM blocks WHERE root_id='?' AND type= 'h'  limit -1" $rootid)}

.action{range $index,$v:=$blocks}
.action{$Htype:=$v.SubType | replace "h" ""}

.action{$intType := int $Htype}
.action{if gt $intType $firstIntType}
.action{$subResult := sub $intType $firstIntType}
.action{$rangeList:=until ($subResult | int)}
.action{range $p:=$rangeList}.action{$tab}.action{end}- ((.action{$v.ID}))

.action{else}							
- ((.action{$v.ID}))
.action{end}


.action{end}

