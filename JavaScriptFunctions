/*
  A JavaScript function for validating a unique number assigned to a runner when they join 
  parkrun, which is then used to identify the runner. The 'runnerID' has to be 
  between 1 and 99999, corresponding to a minimum of 1 digit to a maximum of 5
  digits.
 */
function validateRunnerID()
{
  var runnerID = document.getElementById('RunnerID').value;
  if ( !(runnerID.match(/^[\d]{1,5}$/)))
  {
  	return "RunnerID must not contain less than one or more than 5 digit characters.\n";
  }
  else  
  {
  	return ""; 
  }
}

/*
  A function for validating a unique number assigned to an event conducted by 
  parkrun, which is then used to identify the event. The 'eventID' has to be 
  between 1 and 99999, corresponding to a minimum of 1 digit to a maximum of 5
  digits.
 */
function validateEventID()
{
  var eventID = document.getElementById('EventID').value;
  if ( !(eventID.match(/^[\d]{1,5}$/)))
  {
  	return "EventID must not contain less than one or more than 5 digit characters.\n"; 
  }
  else  
  {
  	return "";  
  }
}

/*
  A function for validating a the date of the event and result. A date must have the
  format YYYY-MM-DD.
 */
function validateDate()
{
  var date = document.getElementById('Date').value;
  if ( !(date.match(/^\d{4}-\d{2}-\d{2}$/)))
  {
  	return "The date entered must match the YYYY-MM-DD date format.\n";
  }
  else 
  {
  	return "";
  }
}

/*
  A function for validating a the time taken by the runner to complete the event. A time 
  must have the format HH:MM:SS.
 */
function validateFinishTime()
{
  var finishTime = document.getElementById('FinishTime').value;
  if ( !(finishTime.match(/^(20|21|22|23|[01]\d)(([:][0-5]\d){2})$/)))
  {
  	return "The finish time entered must match the HH:MM:SS time format.\n";
  }
  else 
  {
  	return "";
  }
}

/*
  A function for validating the runner's finishing position, which is within the range of 
  1 to 10000, corresponding to a minimum of 1 digit to a maximum of 5 digits.
 */
function validatePosition()
{
  var position = document.getElementById('Position').value;
  if ( !(position.match(/^[1-9]?[0-9]?[0-9]?[0-9]{1}$|^10000$/)))
  {
  	return "Position must not contain less than one or more than 5 digit characters.\n"; 
  }
  else  
  {
  	return ""; 
  }
}

/*
  A function for validating the classification of the runner by age and gender, 
  which is within the range of 1 to 100, corresponding to a minimum of 1 digit to a maximum of 2 digits.
 */
function validateCategoryID() 
{
  var categoryID = document.getElementById('CategoryID').value;
  if ( !(categoryID.match(/^[1-9]?[0-9]{1}$|^100$/)))
  {
  	return "CategoryID must not contain less than one or more than 2 digit characters.\n"; 
  }
  else  
  {
  	return "";  
  }
}

/*
  A function for validating the 'AgeGrade', which is a calculated number that gives an 
  indication of how well the runner has done, relative to their gender and age. 
  The 'AgeGrade' needs to have a format of a percentage with two decimal places. 
 */
function validateAgeGrade()
{
  var ageGrade = document.getElementById('AgeGrade').value;
  if ( !(ageGrade.match(/^\d*\.?\d*[1-9]+\d*$|^[1-9]+\d*\.\d*$/)))
  {
  	return "The AgeGrade entered must have a two decimal places percentage format.\n";
  }
  else 
  {
  	return "";
  }
}  

function validate() 
{
  var result = validateRunnerID() + validateEventID() + validateDate() + validateFinishTime() + validatePosition() + validateCategoryID() + validateAgeGrade(); 
  alert("Result = " + result); // shows nothing if fields validate
  if (result == "")
  {  
  	alert("Returns true");
    return true; 
  }
  else 
  {
    alert("Errors");
    return false;
  }  
}
