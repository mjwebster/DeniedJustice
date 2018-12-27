


July 18:
I met today with Christina Knudson, a statistics professors in the mathematics department at St. Thomas University. She helped me run a logistic regression on the project data. 

She recommended that I first exclude records where ALL the key variables we are using are coded as “unknown,” so I added that to my code and also excluded any records where the “sent for prosecution” field is unknown, since that is the dependent variable we are using. This ended up taking out about 30 records out of more than 1,000.

I also set up my code so that it creates new binary values (a 1 or a 0) for the variables I want to use. For example, it creates a new field called involve that is 1 if the victim cooperated throughout the process and a 0 if she did not. It’s NA if we don’t know.

I ran a first batch of models using “sent for prosecution” as the dependent variable. Next I want to try using “charges filed” and see if it comes up with anything radically different. 

I asked Christina if I could run past her any wording that we plan to use in the stories and she said most definitely yes she could help with that. 
Also, she asked if she could get a copy of our data when we’re done. She’d like to use it in her teaching.

-----------------------------
Email to reporters based on my findings:

I’ve got 2 big findings from the regression analysis that you can start noodling.
 
The main thing to know before you look below is that the way this particular regression analysis works is that it allows you to put in several variables – key factors that influence the outcome of a case – and then see which of them have the biggest influence on that outcome. I tried running this with sent for prosecution as the outcome, and then separately as charges filed as the outcome. The charges filed one comes back with better results.
 
I tried many different factors and then winnowed out ones that have little or no impact. Ultimately I found that these factors were the strongest – victim involvement, whether it’s stranger or acquaintance case, whether there was a delay in reporting and whether there was a named suspect.   When you include multiple factors like this, then your results allow you to say that this finding holds true regardless of all these other factors.   
 
 
Key findings:
The odds of charges being filed are 25 times greater if the victim cooperates throughout the case, even after accounting for other factors such as victim involvement, whether they have a named suspect and whether there was a delay in reporting the case.
 
The odds of charges being filed are nearly 4 times greater if the perpetrator was a stranger to the victim, even after accounting for other factors such as victim involvement, whether they have a named suspect and whether there was a delay in reporting the case.   (Another way to think of this is that if they have two cases where victims are both cooperating, they have named suspects and there wasn’t a delay – but one is a stranger case and the other is an acquaintance case – the stranger case is more likely to result in charges filed.)
 
Unfortunately, it’s not giving me any significant findings regarding intoxicated victims or not. It’s showing that the odds are just slightly lower that charges will be filed (or that it would be sent for prosecution) if the victim is intoxicated, but it’s not enough to call that a good finding.
 
When I get back, I need to run my analysis and the wording on these past the professor who helped me. Perhaps she will catch something I missed, as well.
