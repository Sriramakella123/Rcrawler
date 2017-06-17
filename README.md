# Rcrawler: A web crawler and scraper using R

Rcrawler is an R package for web crawling web sites and extracting structured data which can be used for a wide range of useful applications, like data mining, information processing or historical archival.
## RCrawler main features  

## Installation 
First make sure to verify Java 64-bit is installed on your computer. Preferably, install both 32-bit and 64-bit .   
```
#check java version
system("java -version")
```
Install the release version from CRAN:
```
install.packages("Rcrawler")
```
*If you got this error: No CurrentVersion entry in Software/JavaSoft registry! Try re-installing Java and make sure R and Java have matching architectures. Then use :*
```
install.packages("Rcrawler", INSTALL_opts = "--no-multiarch")
```
Or the development version from github:
```
# install.packages("devtools")
devtools::install_github("salimk/Rcrawler")
```
## How to use Rcrawler
In order to show you what Rcrawler brings to the table, we’ll walk you through some use case examples:
Start by loading the library
```
library(Rcrawler)
```

###### 1- Collecting all web pages of a specific website
```
Rcrawler(Website = "http://www.glofile.com", no_cores = 4, no_conn = 4)
```
This command allows downloading all HTML files of a website from the server to your computer. It can be useful if you want to do analysis on the whole web page (HTML file). Also, if you want to use a specific data extraction technique on collected web pages.

At the end of crawling process this function will return :

- A variable named "INDEX" in your global environment: It's a data frame representing the generic URL index, which includes all crawled/scraped web pages with their details (content type, HTTP state, the number of out-links and in-links, encoding type, and level). 

- A directory named as the website's domain, in this case, "glofile.com" it's by default located in your working directory (R workspace). This directory contains all crawled and downloaded web pages (.html files). Files are named with the same numeric "id" they have in INDEX.

###### 1- Collecting all web pages of a specific website

NOTE: Make sure that the website you want to crawl is not so big, as it may take more computer resources and time to finish. Stay polite, avoid overloading the server, the chance to get banned from the host server is bigger when you use many parallel connections. 

## Design and Implementation
If you want to learn more about web scraper/crawler architecture, functional properties and implementation using R language, you can download the published paper for free from this link :  [R web scraping](http://www.sciencedirect.com/science/article/pii/S2352711017300110)
## How to cite Rcrawler
Our paper is submitted, you can cite our work

###### APA :
`
Khalil, S., & Fakir, M. (2017). RCrawler: An R package for parallel web crawling and scraping. SoftwareX, 6, 98-106.
`

###### Bibtex :
`
@article{khalil2017rcrawler,
  title={RCrawler: An R package for parallel web crawling and scraping},
  author={Khalil, Salim and Fakir, Mohamed},
  journal={SoftwareX},
  volume={6},
  pages={98--106},
  year={2017},
  publisher={Elsevier}
}
`
