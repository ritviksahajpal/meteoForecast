meteo
=====

Retrieve NWP-WRF output from Meteogalicia and OpenMeteo services

# Install #

	tmp <- paste0(tempdir(), '/meteo.zip')
	download.file('https://github.com/oscarperpinan/meteo/archive/master.zip',
              destfile=tmp, method='wget')
	unzip(tmp, exdir=tempdir())
		
	## Install dependencies only if you don't have them already.
	install.packages(c('raster', 'zoo')
	install.packages('ncdf4')
	## ncdf4 is not available for Windows at CRAN.
	## Install ncdf4 from http://cirrus.ucsd.edu/~pierce/ncdf/ or use ncdf instead
	## install.packages('ncdf') 
	install.packages(paste0(tempdir(), '/meteo-master'), repos=NULL, method='source')

# Usage #

    library(meteo)
    
    x <- getRaster(var='swflx', day='2014-01-14')
    
    x2 <- getRaster(var='temp', day='2014-01-14')
    
    p1 <- getPoint(3, 35, day='2014-01-14', vars=c('temp', 'swflx'))

