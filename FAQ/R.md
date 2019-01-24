**目录**

[TOC]

## 1. 数据处理

### 1.1  `switch()` 报错—`EXPR must be a length 1 vector`

这里主要指的是在需要利用向量化方法来处理数据的过程出现了一些报错信息，例如:

```R
> i <- function(x){
+     switch (x,
+         成功认证 = 1,
+         未成功认证 = 0,
+         NULL
+     )
+ }
# 这里使用了 purr 包
> map_at(.x = test, .at = c(1), .f = i(.))
Error in switch(x, 成功认证 = 1, 未成功认证 = 0, NULL) : 
  EXPR must be a length 1 vector
```

这个报错信息是因为 `switch()` 函数在处理数据的过程中，因为它不具有向量化方法导致不能对数据进行下一步向量方式处理。如果要处理这个问题可以对函数添加一个 `Vectorize()` 函数，这样就可以完成数据处理：

```R
> i <- Vectorize(function(x){
+     switch (x,
+         成功认证 = 1,
+         未成功认证 = 0,
+         NULL
+     )
+ })

> map_at(.x = test, .at = c(1), .f = i(.))
```

**Note：** 这个方法比较低效，毕竟还有调用另外循环。可以采用更高效的方式，使用 `case_when()`——它在 `dplyr` 包中。