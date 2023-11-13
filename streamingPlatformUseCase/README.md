This is a demo for the use case of a streaming platform. Here we want to verify the following:
 - The user that is logged in meets the requirements for viewing content in that region (e.g. over 15 for violence). This involves:
   - Getting trustworthy information about the requirements for that Juristiction
   - Getting trustowrthy information about the user
   - If it is a parentally controlled setting then it could also negotiate with the parental controls defined in the guardians pod (where the guardian is defined by the govt.)
 - The user has paid the service *without requiring the payment flow within the app* (the user has preferences for how they like to pay; the application has account details for how they like to be Paid.)
   - This payment could be verified in a few ways; including:
     - Treating their bank, crypto wallet etc. as a source of trust as to what references have been made; and having a correlation between the reference number
       and the users WebId (e.g. some form of hash).

 - The application defers to IMDB for 

### !IMPORTANT NOTE!
For monetisation one would take this to movie platforms as a concept. However, a major benefit of this is that
it will also make it easier for people to self-publish and have the right censoring & payment methods in place (becuase everything can be cleanly decoupled; yay!)

### Modelling note:
We are taking some shortcuts here for the moment in that some of our facts are temporally dependent when, in fact,
all of our facts should be globally true. One way to reconcile this is by having a wrapping trust / precondition of
the time the actions are being performed; however, it would be better just to make all of the statements true temporally.

In this way, the subscriptions could actually look like the following set

?user ex:subscriptions [
  a ex:MonthlySubscription ;
  ex:start 1699893952799 ;
  ex:end 1699896544799 .
] .

**NOTE:** The requirement for temporal context could be introduced by the rest of the system either by responding to the
?user acl:read ?movie . question with "I need the current time as a fact for me to be able to evalute this" which the
system can answer; or 
