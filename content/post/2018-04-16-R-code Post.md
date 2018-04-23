+++
date = 2018-04-16
draft = false
tags = ["R", "hyperspec"]
title = "First post with R code - highligh testing"
summary = """
This is example of R code embedded into post.
"""
math = false
+++


## Including Code
```{r}
library(ggplot2)
library(hyperSpec)

setwd("D:/ISMI_ENVI")
wavenumbers1 <- unlist(read.table("wavenumbers1.txt", quote="\"", comment.char=""))
spc1 <- read.ENVI ("Hair_7v5_area1_NB_8_256S.0.img", wavelength = wavenumbers1)
plotmap(spc1, col.regions = matlab.palette)

qplotspc(mean(spc1),colour="red")+ geom_ribbon (aes (ymin = mean + sd, ymax = mean - sd, y = 0, group = NA),
                                                alpha = 0.25,data = as.t.df (mean_sd (spc1)))+scale_x_reverse()+
  labs(x=expression(bold(paste ("Wavenumber", " [",cm ^-1, "]"))), y = "Absorbance [a.u.]" )


plotmap(spc1[,,1500~1400], col.regions = matlab.palette)
```

