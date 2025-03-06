# sen2rts-installation-guidelines
Set of instruction to install the R package sen2rts and all its dependencies updated to February 2025
1) you will need to install "remotes" package to install packages from GitHub: write on your R console *install.packages("remotes")*;
2) you will need to install rgdal. rgdal package is no more on live CRAN but you can go to CRAN archive and download the latest version (here https://cran.r-project.org/src/contrib/Archive/rgdal/rgdal_1.6-7.tar.gz). After downloading it, write in the R console *install.packages("YOUR/PATH", repos = NULL, type = "source")* to install the rgdal package. Equivalently you can install from r-forge using the following *url <- "https://download.r-forge.r-project.org/bin/windows/contrib/4.4/rgdal_1.6-7.zip"* and *install.packages(url, type="source", repos=NULL)*;
3) you will need to install gdalUtils. We are going to use the remotes package. Type on R console the command *remotes::install_github("gearslaboratory/gdalUtils")*
4) in the same way you will install rgeos by typing on the R console the command *remotes::install_version("rgeos", version = "0.6-4")*
5) you will need to install sen2r. As for rgdal, it is not on R CRAN live but you can find it in CRAN archive (here https://cran.r-project.org/src/contrib/Archive/sen2r/sen2r_1.6.0.tar.gz). After downloading it, write in the R console *install.packages("YOUR/PATH", repos = NULL, type = "source")* to install the sen2r package.
6) you will install sen2rts from GitHub using on the R console *remotes::install_github("ranghetti/sen2rts")*.

Possible sources of issues:
1) be sure to have Rtools to install packages from sources. If you cannot remember, install from CRAN the following packages writing on R console the following *install.packages("pkgbuild")*, *install.packages("devtools")*. Then restart R and execute *library(devtools)*, *library(pkgbuild)*, *find_rtools()*. The echo value TRUE means that you have already installed Rtools. Rtools can be found in R-CRAN website according to your current version of R. Your R version can be found using the command *R.version* in the R console;
2) some packages might have been compressed. Try to install the following packages used to (de)compress R packages. Write on the R console the following *install.packages("deflateBR")* and *install.packages("zlib")*
3) other packages have gone deprecated related to R and json. Try to install the following packages writing on the R console *install.packages("XML")* *install.packages("geojsonio")* *install.packages("RcppTOML")*

sen2rts is a package made by L. Ranghetti and you can find info at https://github.com/ranghetti/sen2rts
