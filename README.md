# Denied Justice


# About this project

Denied Justice, www.startribune.com/deniedjustice, was a series of 9 stories published between July and December 2018, by Brandon Stahl, Jennifer Bjorhus and MaryJo Webster. Photographer: Renee Jones Schneider. Editors: Dave Hage and Abby Simons. Digital designer: Anna Boone. Print designer: Greg Mees. 

The series revealed systemic failures by police, prosecutors and judges in how sexual assault cases are handled by the criminal justice system. The backbone of the project was a database built by the Star Tribune from thousands of police reports. The database tracked key components of a case, including whether police took basic investigatory steps, and the outcomes of each case. This data was unique because criminal cases are not tracked from start (when reported to police) to finish (conviction). Our database allowed us to show that the share of reported rapes that result in conviction is less than 1 in 10. And that only about one-quarter of cases are even sent to a prosecutor. We showed that, too often, police do very little investigative work on these cases, often failing to interview all potential witnesses or even talk to a named suspect. 

To bring the data findings to life, reporters went to great lengths to find victims who had reported sex assaults. Their stories backed up our findings -- investigators who didn't believe them, who questioned why they did things, or why they didn't fight back. Some told about months of unreturned phone calls to investigators, or not even knowing that their cases were closed until we told them. For the first story, we had about a dozen women telling their stories on videos and in vignettes with the printed edition. With our stories, we asked other victim/survivors to come forward and by the end of the year we had more than 90 women (no men, unfortunately) who had reached out to us.

# About the data

We filed public records requests with the 20 law enforcement agencies in Minnesota that reported the most rapes to the FBI in 2015 and 2016. From the two largest -- Minneapolis and St. Paul -- we asked for all closed sexual assault cases that were reported in 2015 and 2016, excluding those involving victims under age 13. 

For the other agencies, we first asked for a list of the case numbers, which some provided in spreadsheets, others in PDFs. We got them all into spreadsheets and used a random number generator to randomly select a 50% sample of the cases. Then we requested those cases from the agencies. Later we discovered that most of those lists of cases included incidents involving victims under age 13, so in the end we didn't get a solid 50% sample. Note: We chose 50 percent because we knew that we'd encounter a good share of "unfounded" cases or that the agency might come back to us and say a case we requested is open and can't be provided (this happened with St. Paul). So we hoped that ultimately we'd end up with 30 to 40 percent samples. Ultimately, all of these things happened and we ended up with about 500 viable cases from these 18 agencies.

Note that we used a broad definition of the kinds of cases; these weren't limited to penetration cases (or the classic "rape" case). These were anything that fell under the criminal sexual conduct statutes in Minnesota, except violations of sex offender registry laws.

In hindsight, we should have first asked all of the agencies for a spreadsheet with the following information on all sexual assaults reported in the time period we wanted: case number, date reported, incident date, closure code, and statute/violation information (this should be either a state statute or something else that indicates something like "Criminal Sexual Conduct 1/Force Used" or "criminal sexual conduct 2/Child under 13"). This statute/violation information would have helped us winnow out cases that weren't applicable.

All of our requests took months, if not years to complete. The Minneapolis request was filed in May 2017. They trickled reports out each week, sending the last batch in November 2018. The request to St. Paul was filed in August 2018; they provided a box of all the paper reports in January 2018. We filed the requests with the other agencies in January 2018. The first of those started coming in April/May, but we had to make a lot of follow-up phone calls and soothe upset records officials who saw our requests as excessively burdensome (primarily because of the extensive redactions required). More records flowed in at the end of summer. But it was November before we got anything from Itasca County Sheriff (just 72 reports requested) and Anoka County (the third largest agency) sent their final batch in December 2018, just as we were finishing up the final stories.

The agencies provided the reports primarily via PDF, but a couple agencies (including St. Paul) gave us paper copies that we had to scan. We set up a process to get the PDFs into our system, for reporters to read them, and enter information into a database. 

First, the PDFs were run through OCR using Adobe Acrobat. We found that sometimes the PDFs were digital to begin with, but we also found some where a few pages were digital and others were photo copies. So just OCRed everything to be safe.

The files were put into a Dropbox account. We set up an instance of Open Semantic Search that linked to that Dropbox directory and pulled in new files at a regular interval. (We used the Dropbox account to store all of the project materials, including rough drafts, in order to have a seamless way to share everything). 

As the files came into Open Semantic, they automatically got a tag we called "Needs review."  Reporters could open Open Semantic (via a web browser) and see the files with that tag. They would find a case to read, tag it with their name ("Reviewed by MaryJo") and remove the "Needs review" tag. Any reports that didn't meet our criteria (i.e. they involved a victim under age 13) were tagged in Open Semantic as "not for database."

After reading a case, the reporters used a data entry form in AirTable to document key pieces of each case. Some things were basic like the case number, department, date of incident, date reported. They also tracked names and dates of birth of suspects, wrote a brief description of the allegations, had a way to flag interesting cases they wanted to come back to, noted if a rape exam had been conducted, and then filled out a series of fields about the investigatory work and the case outcomes.

We relied on advice from experts and documents/videos about best practices in investigating (and documenting) sex assault investigations that were developed by the International Chiefs of Police and other organizations. We spent many weeks debating what should be tracked and exactly how. We quickly realized that some of the things we hoped to track wouldn't be possible because we only had access to whatever was put into documentation. For example, we wondered if we could track whenever we saw instances of police using biased language. We didn't find this very often in the case files and we also realized that this might be something that occurred but maybe didn't end up in the written report. So we scrapped that plan.

Ultimately, we realized that our best course was to simply track basic investigatory steps -- did the detective interview the victim, did they interview a named suspect, did they interview all potential witnesses, did they collect all potential evidence, did they go to the crime scene. Some of these things became not applicable due to delays in reporting. For the witnesses and evidence, we noted cases where there were witnesses or potential evidence listed in the report that wasn't followed through on. For example, a narrative might have mentioned that there could be surveillance video at a nearby business, but the police report didn't document that it had been collected. We frequently found cases where the reports listed potential witnesses -- not necessarily eye-witnesses, but people who saw the victim and/or suspect either before or after the incident -- but that investigators never reached out to them.

The police reports typically indicated if the case was sent to prosecutors. But we also found that the reports rarely listed a "closure" code -- i.e. that the case was closed by arrest, or exceptionally cleared, etc. The majority of reports we read either didn't list a closure or were "inactive". 

To track whether charges were filed and whether there was a conviction, we used the suspect names/DOBs to search court records. We ran into some situations where agencies redacted suspect information, even when the suspect was an adult (it is legal in MN for them to redact suspect information for juveniles). For example, Rochester redacted the suspect info for the majority of their cases. We reached out to them and asked if they would provide us a spreadsheet with the case numbers and suspect information. And they did. 

After we had several hundred cases entered into AirTable, I set up this R project to do data cleanup and analysis. Doing this work in R was invaluable because we wanted to start running the analysis before we had a complete set of data, then we needed to re-run the analysis again and again, as more data rolled in.

The import/cleanup script pulls in a csv (which we had to manually download from AirTable), skips some fields and renames pretty much all of them. (Our AirTable file contained a lot of fields we added at the outset then stopped using as we discovered we couldn't get what we intended out of the reports). 

The script also identifies and excludes cases deemed "unfounded" and those that were reported prior to 2015. (Brandon requested some data going back to 2010 from the University of Minnesota and Minneapolis police during his initial digging on this topic. Those files were entered into AirTable but not used as part of the analysis). It also excludes some cases from agencies that weren't part of our 20. These are cases that reporters obtained for incidents involving the victim/survivors we interviewed for the stories. (We required a police report in our hands before publishing anything about a victim)

The script also creates a lot of new fields, generally recoding existing variables. For example, it creates a "delay" field by calculating the difference between the reported date and the incident date and creates a field to indicate if there is a named suspect or not (this is a field I wish we had added on the front end, but the AirTable form only has a spot for reporters to list suspect names). A lot of this recoding was added at the analysis phase once I realized that I needed a particular variable but our data wasn't quite set up the right way. If someone were to replicate this work, I'd start by studying the load data script to see all the recoding that was done and figure out what could be avoided by building the data entry form correctly to start with.

Read more about our process here: https://source.opennews.org/articles/how-we-built-database-thousands-police-reports/

# Scripts:

--<strong>load_clean_data.R</strong> --  This is a script that pulls in the csv file (downloaded from Airtable) and does a long series of cleanups and adding fields. Need to run this before trying to work with any of the RMarkdown pages

# RMarkdown pages:
The following markdown pages contain the analyses used.

--<strong>rape2018.rmd</strong> -- this is the weekly analysis page that was the first thing I built. Think of this as a sort of working document where I tried out various theories, mostly using cross tabulations. You'll see a lot of crossover between this and the subsequent files.

--<strong>highlights.rmd</strong> -- this is where you'll find the high-level findings that ended up in the story and were shared with public officials. It doesn't match the graphics, however. (the graphics split resulted into cases that were sent for prosecution and those that were not. You can find those resulted in the "buckets" section of rape2018)

--<strong>liquor.rmd</strong> -- this contains the main findings for the 3rd story about victims who are intoxicated

--<strong>sample.rmd</strong> -- this is a trial I ran to see if using a random sample of Minneapolis and St. Paul cases (instead of the full number of cases) resulted in any wildly different findings than if I just used all the cases we have. Keep in mind that the data from the other agencies was already a random sample.

--<strong>threebuckets.rmd</strong> -- this is an attempt to look at the case grouped into three categories: those that were never assigned to prosecutors, those that were investigated but not sent for prosecution and those that were investigated and sent for prosecution. I was pitching this as a way to present the data graphically, but they ended up going with 2 buckets. 

--<strong>top4.rmd</strong>  -- this compared the 4 agencies with the largest number of cases against each other on our key metrics.

--<strong>sentence2.rmd</strong>  -- this uses data from the Sentencing Guidelines Commission to look at sentencing patterns of those convicted of felony criminal sexual conduct between 2008 and 2017. This was used for story #7. See the file called "README_sentencing_data.txt" for details

--<strong>bcamajorcrimes.rmd</strong> - this uses data from the MN Bureau of Criminal Apprehension on the number of reported rapes in each jurisdiction each year, between 2010 and 2016. This is what we used to determine which 20 agencies to include in our analysis.

--<strong>rcao.rmd</strong>  -- This uses data from the Ramsey County Attorney's office. This is their attempt to do a similar analysis of sexual assault cases in Ramsey County. They used a smaller sample of cases, but collected far more pieces of information about each one. 

--<strong>regression.rmd</strong> -- This is my attempt at a regression analysis on the data, which was never put to use. See README_regression for more details.

# Data:
--<strong>RapeProject2018-MaryJoExportView</strong> -- this is the main data file exported from AirTable; a backup of this has been imported to the MySQL server in the "crime" database.

--<strong>fields.xlsx</strong> -- this is a record layout of the Airtable file, including some of the info I used for building the import script

--<strong>BCA_majorcrimes.csv</strong> -- this is the data from MN Bureau of Criminal Apprehension, used for the bcamajorcrimes.rmd analysis

--<strong>ramsey_county_attorney_data.zip</strong> -- this is data and record layout from Ramsey County Attorney's office

--Sentencing data is stored in the sentencing sub-directory.


# Questions?

Contact @MaryJoWebster




