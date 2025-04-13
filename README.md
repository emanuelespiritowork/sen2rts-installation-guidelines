# sen2rts-installation-guidelines
Set of instruction to install the R package sen2rts and all its dependencies updated to February 2025
1) you will need to have *Rtools* installed. To check it, go into issue section of this guide; 
2) you will need to install *remotes* package to install packages from GitHub: write on your R console:
```r
install.packages("remotes")
```
3) you will need to install *rgdal*. rgdal package is no more on live CRAN but you can go to CRAN archive and download the latest version (here https://cran.r-project.org/src/contrib/Archive/rgdal/rgdal_1.6-7.tar.gz). After downloading it, to install the *rgdal* package write in the R console: 
```r
install.packages("YOUR/PATH", repos = NULL, type = "source")
#Equivalently you can install from r-forge using the following:
url <- "https://download.r-forge.r-project.org/bin/windows/contrib/4.4/rgdal_1.6-7.zip"
install.packages(url, type="source", repos=NULL)
```
4) you will need to install *gdalUtils*. We are going to use the *remotes* package. Type on R console the command: 
```r
remotes::install_github("gearslaboratory/gdalUtils")
```
5) in the same way you will install *rgeos* by typing on the R console the command: 
```r
remotes::install_version("rgeos", version = "0.6-4")
```
6) you will need to install *sen2r*. As for *rgdal*, it is not on R CRAN live but you can find it in CRAN archive (here https://cran.r-project.org/src/contrib/Archive/sen2r/sen2r_1.6.0.tar.gz). After downloading it, write in the R console:
```r
install.packages("YOUR/PATH", repos = NULL, type = "source")
```
7) you will install *sen2rts* from GitHub using on the R console:
```r
remotes::install_github("ranghetti/sen2rts")
```

Possible sources of issues:
1) remember not to update any package while installing one of the previous ones. CRAN will always check if there are updates for dependent packages while you install a new one. Please select not to update packages. If you have already updated a package of interest, remove and then start the list above again. 
2) be sure to have *Rtools* to install packages from sources. If you cannot remember, install from CRAN the following packages writing on R console the following:
```r
install.packages("pkgbuild")
install.packages("devtools")
#Then restart R
library(devtools)
library(pkgbuild)
find_rtools()
#The echo value TRUE means that you have already installed Rtools.
#Rtools can be found in R-CRAN website according to your current version of R.
#Your R version can be found using the command in the R console:
R.version
```
2) some packages might have been compressed. Try to install the following packages used to (de)compress R packages. Write on the R console the following:
```r
install.packages("deflateBR")
install.packages("zlib")
```
3) other packages have gone deprecated related to R and json. Try to install the following packages writing on the R console:
```r
install.packages("XML")
install.packages("geojsonio")
install.packages("RcppTOML")
```
4) check *sp* package version (it should be 2.1-4). It should be the one you get from:
```r
remotes::install_version("rgeos", version = "0.6-4")
```
sen2rts is a package made by L. Ranghetti and you can find info at https://github.com/ranghetti/sen2rts. Full documentation is found at https://rdrr.io/github/ranghetti/sen2rts/
