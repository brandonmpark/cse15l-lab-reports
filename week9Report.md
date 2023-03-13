# Week 9 Report: Report 4 Expanded

In order to very quickly accomplish the task using a bash script, we could simply put all of the commands after logging into ieng6 into a bash script, which we then run on the remote. The bash script would look something like the following:

```bash
# befast.sh

# clone the repo
git clone git@github.com:brandonmpark/lab7.git 

# run the tests (incorrect)
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExampleTests

# fix the code
sed -i '43 s/1/2/1' ListExamples.java

# run the tests (correct)
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExampleTests

# commit the changes
git add ListExamples.java
git commit -m "Edited ListExamples.java"
git push
```

In order to run the script (assuming stored in the home directory) on the remote, we could pass it into `ssh` as so: `ssh cs15lwi23akr@ieng6.ucsd.edu 'bash -s' < ~/befast.sh`.
