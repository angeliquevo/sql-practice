
## Case 1


## Output 2

  Description

```bash
> mystoredata.df <-read.table(path,
+                             header = TRUE,
+                             sep = ",",
+                             stringsAsFactors = TRUE)
> dim(mystoredata.df)
[1] 216   5
> aggregate(salesthisyear ~ segment, data=mystoredata.df, mean)
       segment salesthisyear
1     CONSUMER      9178.078
2 PROFESSIONAL      6040.267
3    SPECIALTY      3804.241
4        VALUE      6031.467

```

