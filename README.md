# Denied Justice





# Scripts:
--<strong>load_clean_data.R</strong> --  This is a script that pulls in the csv file (downloaded from Airtable) and does a long series of cleanups and adding fields. Need to run this before trying to work with any of the RMarkdown pages

#RMarkdown pages:
The following markdown pages contain the analyses used.

--<strong>rape2018.rmd</strong> -- this is the weekly analysis page that was the first thing I built. Think of this as a sort of working document where I tried out various theories, mostly using cross tabulations. You'll see a lot of crossover between this and the subsequent files.

--<strong>highlights.rmd</strong> -- this is where you'll find the high-level findings that ended up in the story and were shared with public officials. It doesn't match the graphics, however. (the graphics split resulted into cases that were sent for prosecution and those that were not. You can find those resulted in the "buckets" section of rape2018)

--<strong>liquor.rmd</strong> -- this contains the main findings for the 3rd story about victims who are intoxicated

--<strong>sample.rmd</strong> -- this is a trial I ran to see if using a random sample of Minneapolis and St. Paul cases (instead of the full number of cases) resulted in any wildly different findings than if I just used all the cases we have. Keep in mind that the data from the other agencies was already a random sample.

--<strong>threebuckets.rmd</strong> -- this is an attempt to look at the case grouped into three categories: those that were never assigned to prosecutors, those that were investigated but not sent for prosecution and those that were investigated and sent for prosecution. I was pitching this as a way to present the data graphically, but they ended up going with 2 buckets. 

--<strong>top4.rmd</strong>  -- this compared the 4 agencies with the largest number of cases against each other on our key metrics.

--<strong>sentence2.rmd</strong>  -- this uses data from the SEntencing Guidelines Commission to look at sentencing patterns of those convicted of felony criminal sexual conduct between 2008 and 2017. This was used for story #7.

--<strong>bcamajorcrimes.rmd</strong> - this uses data from the MN Bureau of Criminal Apprehension on the number of reported rapes in each jurisdiction each year, between 2010 and 2016. This is what we used to determine which 20 agencies to include in our analysis.

--<strong>rcao.rmd</strong>  -- This uses data from the Ramsey County Attorney's office. This is their attempt to do a similar analysis of sexual assault cases in Ramsey County. They used a smaller sample of cases, but collected far more pieces of information about each one. 

--<strong>regression.rmd</strong> -- This is my attempt at a regression analysis on the data, which was never put to use. See README_regression for more details.

# Data:
--<strong>RapeProject2018-MaryJoExportView</strong> -- this is the main data file exported from AirTable; a backup of this has been imported to the MySQL server in the "crime" database.

--<strong>fields.xlsx</strong> -- this is a record layout of the Airtable file, including some of the info I used for building the import script

--<strong>BCA_majorcrimes.csv</strong> -- this is the data from MN Bureau of Criminal Apprehension, used for the bcamajorcrimes.rmd analysis

--<strong>ramsey_county_attorney_data.zip</strong> -- this is data and record layout from Ramsey County ATtorney's office


# Sentencing:
See the file called "README_sentencing_data.txt" for details



