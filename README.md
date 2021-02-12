## Connection Page
- address mail type email 
- password type password
- submit type button 

# Validation 
- address mail is not empty 
- password is not empty 
Process Submit : validated 
DO 
- check database if email = password 
Process Submit : not validated 
DO 
- check database if email != password 
errorMessage  : "Your email and password is not valid"

## ShowAllConges Page
# First Table : 
- requestConges type button 
- employeeId type/label NotModified
based on employeeEmail-login
- employeeName type/label NotModified
based on employeeEmail-login
- idTypeConges type/string
check database : show all congés id based with employeeId
- nameTypeConges type/string
check database : show all congés name  based with employeeId
- expiredDate type/date
check database : when congés must be taken, if not it will expired
- totalDays type/number
check database : totalDays for each idTypeConges

# Second Table
Conges Request Summary 
- congesRequestId 
check database : check all the request congés that has been madr by employeeId
- statusCongés 
1. Waiting for Approval 
2. Approved 
3. Request for Annulation 
4. Annuled
5. Rejected 
- Periode Date 
dateStarted / dateFinished label NotModified



## Form RequestConges Page
- employeeId type label NotModified
- employeeName type label NotModified
- typeConges type DropDownList
DropDownList avec nameTypeConges - idTypeConges
- comment type text
- dateStarted , dateFinished type date
- submit type button 

# Validation
- typeConges
check database : show all congés name + all congés id
- dateStarted : 
can't empty
can't less then 30 days from today
- dateFinished : 
can't empty
can't bigger 30 days 
check database : show only the periode that valid with the totalDays existed 
- Process Submit : 
When form is valid :
DO 
* Send email to email idEmployee 
* Send email to email manager of idEmployee 
* Show the request congés in ## ShowAllConges Page with status : Waiting for Approval 

* Status congés / 
1. Waiting for Approval 
2. Approved 
3. Request for Annulation 
4. Annuled
5. Rejected 

When form is not valid :
errorMessage = "There is a probleme of your request. Please contact HR administrator "






