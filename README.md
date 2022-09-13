# leuka
library(MASS)
library(survival)
leuk.cox<- coxph(Surv(time)~ag+log(wbc),data = leuk)
summary(leuk.cox)
str(leuk)
plot(survfit(Surv(time)~ag,data = leuk),xlab = "t",ylab = "S(t)",
     lty =2:3,log = T )
legend(80,0.8,c("ag absent","ag present"),lty = 2:3)
