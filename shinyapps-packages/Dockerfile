FROM thirupathip/shinyapps
 
RUN apt-get update -qyy
# basic shiny functionality

RUN R -e "install.packages(c('rio', 'sjmisc' , 'RColorBrewer', 'flextable'))"

RUN mkdir -p /app/Shiny
COPY app_monthly_report /app/Shiny
COPY Rprofile.site /usr/lib/R/etc/
EXPOSE 3838

CMD ["R", "-e", "shiny::runApp('/app/Shiny')"]
