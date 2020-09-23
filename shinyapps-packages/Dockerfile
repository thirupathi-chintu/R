FROM thirupathip/shinyapp-dep:3.5.2
 
RUN apt-get update -qyy
# basic shiny functionality
RUN R -e "install.packages(c('shiny', 'shinycssloaders', 'dplyr', 'jpeg', 'pracma', 'data.table', 'DT', 'shinyjs', 'shinyBS'), repos='http://cran.rstudio.com/')"# copy the app to the image

RUN R -e "install.packages(c('shiny', 'tsibble', 'visdat', 'RcolorBrewer', 'zip', 'imputeTS', 'ggrepel', 'auth0', 'tidyverse', 'shinydashboard', 'dplyr', 'shinyjs', 'DT', 'RMariaDB', 'glue', 'stringi', 'lubridate', 'DBI', 'shinyalert', 'shinythemes', 'shinycssloaders', 'plotly', 'shinyWidgets', 'RVerbalExpressions', 'tidypredict', 'dygraphs', 'grid', 'gt', 'ggtext', 'openxlsx', 'shinyjs', 'formattable', 'ggridges', 'patchwork', 'janitor', 'xts', 'RMariaDB', 'aws.s3'), repos='http://cran.rstudio.com/')"
RUN R -e "install.packages(c('ggiraph', 'slider', 'webshot', 'kableExtra', 'xtable', 'huxtable', 'rmarkdown', 'gridExtra', 'magick', 'ggplot2'), repos='http://cran.rstudio.com/')"

RUN R -e "install.packages(c('fitdistrplus', 'foreach', 'shinycustomloader', 'schoolmath', 'rWind', 'hablar', 'naniar', 'grid', 'cowplot', 'googlesheets4', 'googledrive', 'circular', 'rdrop2', 'repmis', 'zoo', 'geosphere'), repos='http://cran.rstudio.com/')"


RUN mkdir -p /app/Shiny
COPY app_monthly_report /app/Shiny
COPY Rprofile.site /usr/lib/R/etc/
EXPOSE 3838

CMD ["R", "-e", "shiny::runApp('/app/Shiny')"]
