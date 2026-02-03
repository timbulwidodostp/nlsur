# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Fitting Iterative Feasible Non-Linear Seemingly Unrelated Regression Model Use nlsur With (In) R Software
install.packages("nlsur", repos = c("https://janmarvin.r-universe.dev", "https://cloud.r-project.org"))
library("nlsur")
# Estimation Fitting Iterative Feasible Non-Linear Seemingly Unrelated Regression Model Use nlsur With (In) R Software
nlsur = read.csv("https://raw.githubusercontent.com/timbulwidodostp/nlsur/main/nlsur/nlsur.csv", sep = ";")
names(nlsur) <- c("Year", "Cost", "Sk", "Sl", "Se", "Sm", "Pk", "Pl", "Pe", "Pm")
eqns <- list( Sk ~ bk + dkk * log(Pk/Pm) + dkl * log(Pl/Pm) + dke * log(Pe/Pm), 
Sl ~ bl + dkl * log(Pk/Pm) + dll * log(Pl/Pm) + dle * log(Pe/Pm), Se ~ be + dke * log(Pk/Pm) + dle * log(Pl/Pm) + dee * log(Pe/Pm))
strtvls <- c(be = 0, bk = 0, bl = 0, dkk = 0, dkl = 0, dke = 0, dll = 0, dle = 0, dee = 0)
nlsur <- nlsur(eqns = eqns, data = nlsur, startvalues = strtvls, type = 2, trace = TRUE, eps = 1e-10)
summary(nlsur)
# Fitting Iterative Feasible Non-Linear Seemingly Unrelated Regression Model Use nlsur With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished