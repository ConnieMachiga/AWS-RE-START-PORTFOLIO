<h1>Challenge Lab: Bash shell scripting exercise</h1>
<h2>Objective:</h2>
<p>In this challenge, I will:</p>
-Create a directory
<h2>My Challenge</h2>
Write a bash script based on the following requirements:
<p><ol>Creates 25 empty (0 KB) files.</ol>
<ol>The file names should be "yourName""number", "yourName""number+1", "yourName""number+2", and so on.</ol>
<ol>Design the script so that each time I run it, it creates the next batch of 25 files with increasing numbers starting with the last or maximum number that already exists.</ol>
<ol>Do not hard code these numbers. I need to generate them by using automation.</ol>
<ol></ol>Test the script. Display a long list of the directory and its contents to validate that the script created the expected files.</ol></p>
<h1>Task : Use SSH to connect to an amazon linux ec2 instance</h1>
<p>Below is a picture showing a successfully connected instance.</p>

<img width="672" height="294" alt="Screenshot 2026-03-17 103505" src="https://github.com/user-attachments/assets/afe17293-621a-406f-8cd9-a04f23f0b66e" />

<h1>Task 2: The Challenge</h1>
<p><b>Step 1</b></p>
<p>Create a directory named "connie_17.01.2026"</p>

<img width="619" height="339" alt="Screenshot 2026-03-17 103958" src="https://github.com/user-attachments/assets/b35012cf-a188-41a0-87f7-743e4e032907" />

<p><b>Step 2</b></p>
<p>Create a bash script</p>

<img width="1352" height="666" alt="Screenshot 2026-03-17 110844" src="https://github.com/user-attachments/assets/da58f211-5980-4229-8f6c-e3eb3cc782d3" />

<h1>Script Explanation</h1>
<p><b>Scrip purpose:</b>This Bash script is designed to automate the creation of files with sequential numbering. Each time it runs, it checks the current directory for existing files that start with a specific name (in this case, “Connie”), determines the highest number already used, and then creates 25 new empty files continuing from that number. This ensures that file names are never duplicated and always follow a consistent sequence.</p>

<p><b>Shebang & Variable Setup:</b>#!/bin/bash yourName=Connie</p>
<ol>#!/bin/bash → tells the system to run this script using Bash</ol>
<ol>yourName=Connie → prefix for all filenames (e.g., Connie1, Connie2)</ol>
<p><b>Extract Existing File Numbers:</b> numbers=$(ls | grep ^$yourName | grep -oE [0-9]+)</p>
<ol>ls → lists all files in the directory</ol>
<ol>grep ^$yourName → filters files starting with "Connie"</ol>
<ol>grep -oE [0-9]+ → extracts only the numbers from filenames</ol>
<p><b>Initialize Variables:</b> declare -i maxNumber=0  declare -i num=0</p>
<ol>-i → forces variables to be treated as integers</ol>
<ol>maxNumber → will store the highest number found</ol>
<p><b>Find the Maximum Number:</b> for (( i=0; i<${#numbers[@]}; i++ ))
do
  num=${numbers[i]}
  if (( num > maxNumber ))
  then
    maxNumber=$num
  fi
done </p>
<ol>Loops through all extracted numbers</ol>
<ol>Compares each number with maxNumber</ol>
<ol>Keeps the largest value</ol>
<p><b>Create 25 New Files:</b> for i in {1..25}
do
  echo "Creating file number $i"
  nextFileName="$yourName$nextNumber"
  echo $nextFileName
  touch $nextFileName
  nextNumber=$nextNumber+1
done</p>
<ol>Runs loop 25 times</ol>

<ol>Creates filenames like:</ol>
Connie11
Connie12
Connie13
...
Connie25
<p>"Touch" creates empty files</p>

<img width="543" height="486" alt="Screenshot 2026-03-17 111254" src="https://github.com/user-attachments/assets/48df9caf-3460-40a0-9d46-74d944373df6" />


<p><b>THE FILES HAVE BEEN CREATED!</b></p>

Challenge complete






