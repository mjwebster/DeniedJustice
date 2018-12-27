About the sentencing data used for Denied Justice

Source: Minnesota Sentencing Guidelines Commission
Submit request for data through their online form: https://mn.gov/sentencing-guidelines/contact/data-requests.jsp

Alternative contacts: Kathleen Madland, kathleen.madland@state.mn.us
or data analyst Anne Wall, anne.wall@state.mn.us

For questions about the data itself, Anne Wall is best source. She knows the data inside and out.

Brandon Stahl initially put in a request for sentencings on all criminal sexual conduct cases, 2008 to 2016. The file he got back is the one called "All_CrimSex_Degrees_original". In the Excel version of that, you'll see that the commission put in fancy column labels but they didn't include all the fields. 

The main missing field that proved problematic for us was called "statute" -- this is a code that the guidelines commission adds to this data after they get it from the courts and county attorneys. For example, "609342130" represents CSC 1, subdivision 1(c) (or "fear of great bodily harm). Anne Wall said this field is the only reliable way to discern which cases involve statutory charges (teenage victims, where consent can't be used as a defense). 

There are fields in the data that refer to the state statute section and subdivisions, but Anne said those fields are unreliable. 

We later discovered the data was also missing a field called "tpsex" which indicated the number of prior felony sex crime convictions the person had (this is important because sentencing is stiffer for repeat offenders)

Ultimately Anne ended up sending us her SPSS file "Add tpsex 2008_2016 (002).sav" and we used that for the analysis. Midway through our work, the 2017 data became available, so she sent us that file separately, "CSC1thr5_2017.sav"

Turns out the fields aren't consistent between the two files. I created a record layout - "sentencing data record layout.xls" that lines them up. 

In my R code -- sentence2.rmd -- I imported each file, stripped them down to only the fields that matched, and renamed fields as needed. Then appended them together.

We did this analysis in a bit of a hurry so I didn't have time to try to ask for all the years in a single file, with all the fields I wanted. 

Note: we also got csv files for aggrevated robbery, murder, manslaughter and assault (2008 to 2016 only). We initially intended to try to see if sentencing patterns were any different for criminal sexual conduct than other major crimes and we found that there wasn't. Departure rates are similar. 

To work with the "statute" field in the CSC data, I used the sentencing guidelines commission document "sentencing guidelines commission Recode2016.docx", then I created my own spreadsheet -- "recode statutes in sentencing data" where I built the R coding necessary to translate the statute codes into two other fields. The first field identifies the crime level (CSC1, CSC2, etc) and the second identifies whether this is a statutory case, a force case, one involving an authority figure, or involves a victim under age 13. (We chose to exclude the under 13 cases; and we essentially ignored the authority figure cases because there are so few)

The statutory case are ones charged under specific sections of the law that apply to victims roughly 13 to 17 years old, and sometimes involving an offender who is significantly older; other times it's a "Romeo and Juliet" situation with two teenagers. Regardless, these are all cases where the offender can't use consent as a defense. These cases represent 65% of all the convictions that we looked at. We thought that was an astounding number, but we have no idea what percentage of victims who report sex assaults are teenagers. We suspect, though, that it's far short of 65 percent. We think these cases make up a disproportionate share of the convictions because they are relatively "easy" cases for the police and prosecutors. They don't have that messy issue of consent to deal with. But these cases also carry very light sentences. In fact, very few spent time behind bars. So if you include these cases in the overall calculations to determine what share of offenders are sentenced to prison, that will skew the percentage to the low side. 

The cases labeled as "Force/Inc" are ones charged under statutes used for cases that involved force, fear of great bodily harm or where the victim was incapacitated (these are rare, since simply being drunk doesn't meet the high threshold for this). In other words, these are the more traditional type of rape cases.

I used the MOC codes to figure out the relationship between the victim and offender, so I could put the cases into buckets like acquaintance, stranger, authority figure, Family, etc.   The PDF called "MOC Table August 2016" breaks down the MOC codes. You need to use the table in there called "criminal sexual conduct" (Table L- page 24)
In the data there are 5 MOC codes - MOC1=L for all the records, MOC2=degree, MOC3=act, MOC4=assailant and MOC5=victim. 
MOC4 was what I used to figure out the relationship between the assailant and victim. MOC5 was another way to figure out which victims were under 13.

FYI...Both the MOC codes and the statute field are used across all the sentencing guidelines commission data, not just the criminal sexual conduct cases. 

Some other important things to know about the sentencing data:
Our analysis was limited to only those cases that were sentenced under the sex offender sentencing grid, which was passed into law in 2006 and started applying to cases in 2008. A case doesn't apply, though, if the crime occurred prior to the grid taking effect. The data includes a field indicating if a case was subject to the grid or not. 

You can find the grid in the back of the guidelines commission report - "2016-MSGC_Crimnal_Sexual_Conduct_Report" (page 56)
The grid is set up with each row representing the severity (A through H) and the columns representing the offenders criminal history score (0 to 6). Anne Wall told us the criminal history score is calculated including both misdemeanors (.5 of a point) and felonies (1 point), but a prior sex crime felony conviction will boost that up significantly. 

The area shaded in grey means cases that fall in these spots on the grid have a presumed "stay" (possibly county jail, and at least probation). All the others have a presumed prison sentence and the grid indicates the range of time. For example, severity A with a criminal history of 0 has a presumed sentence of 144 to 172 months in prison. 

In the data, you'll find fields called "severity" and "history" that match these grid levels. Also there is a field called "presumpt" that indicates whether the presumptive sentence is "prison" or "stay".  That was a key field for isolating the cases that had a presumed prison sentence to then look at which ones got a downward dispositional departure (and got jail time). One of our key findings was that 32% of acquaintannce cases that started out with a presumed prison sentence got a downward departure, while just 15% of stranger cases. (This is likely due to the fact that most acquaintance cases have a 0 criminal history score.)

The field called "inctype" indicates the ultimate sentence as being "state prison", "Cond Jail" (jail with conditions) or "other sanctions" (probation only). All sex offenders are required to be on probation for some period of time after their incarceration, plus they are placed on the sex offender registry.










