<?php
  $runnerID = $_POST['RunnerID'];  
  $eventID = $_POST['EventID'];
  $date = $_POST['Date'];
  $finishTime = $_POST['FinishTime'];
  $position = $_POST['Position'];
  $categoryID = $_POST['CategoryID'];
  $ageGrade = $_POST['AgeGrade'];
  $pb = $_POST['PB'];
	
  //connect to database

  $host = 'tt284.open.ac.uk';
  $username = 'dpb285';
  $password = 'nfCnRSvT';
  $dbname = 'dpb285_db';

  $connection = mysql_connect($host, $username, $password)
  or die( 'connection error:' . msql_error());

  mysql_select_db($dbname)
  or die('Database selection problem: ' . mysql_error());

  //show table

  $sql = 'select * from Results';
  $result = mysql_query($sql, $connection);

  echo "<table>";
  while ( $row = mysql_fetch_array($result) )
  {
    echo "<tr><td>";
    echo $row['RunnerID'];
    echo "</td><td>";
    echo $row['EventID'];
    echo "</td><td>";
    echo $row['Date'];
    echo "</td><td>";
    echo $row['FinishTime'];
    echo "</td><td>";
    echo $row['Position'];
    echo "</td><td>";
    echo $row['CategoryID'];
    echo "</td><td>";
    echo $row['AgeGrade'];
    echo "</td><td>";
    echo $row['PB'];
    echo "</td></tr>";
 }
 echo "</table>";

 $sql="INSERT INTO Results (RunnerID, EventID, Date, FinishTime, Position, CategoryID, AgeGrade, PB) VALUES ('$runnerID', '$eventID', '$date', '$finishTime', '$position', '$categoryID', '$ageGrade', '$PB')";
 
 $outcome = mysql_query($sql,$connection);
 $positive = true;
 $negative = false;
 if ($outcome = $positive)
 {
   echo '<h2>Success! Saving data:</h2>';
   echo "RunnerID = ".$runnerID;
   echo "<p></P>";
   echo "EventID = ".$eventID;
   echo "<p></P>";
   echo "Date = ".$date;
   echo "<p></P>";
   echo "FinishTime = ".$finishTime;
   echo "<p></P>";
   echo "Position = ".$position;
   echo "<p></P>";
   echo "CategoryID = ".$categoryID;
   echo "<p></P>";
   echo "AgeGrade = ".$ageGrade;
   echo "<p></P>";
   echo "PB = ".$pb;
   echo "<p></P>";
 }

 return $connection;
?>
