# Week 7 Lab Report

## Step 4: Logging into ieng6

<img width="506" alt="Screenshot 2023-02-26 at 12 55 37 PM" src="https://user-images.githubusercontent.com/25190789/221436753-932a56c8-68ca-4c47-9253-e466ae29f457.png">

The first step is logging into ieng6, which I accomplished by simply typing in the command `ssh cs15lwi23akr@ieng6.ucsd.edu<enter>`. There is no way I know of to expedite this command besides copy-pasting it in.

## Step 5: Cloning the forked repository

<img width="560" alt="Screenshot 2023-02-26 at 12 57 15 PM" src="https://user-images.githubusercontent.com/25190789/221436863-bd377bec-aa7c-4f8d-8bb6-e8a05c6eeed7.png">

The next step is cloning the repository, which I accomplished by typing in `git clone <^v><enter>`, having copied (`<^c>`) the `git@github.com:brandonmpark/lab7.git` url from the GitHub repository. I then navigated into the directory by typing in `cd l<tab><enter>`, using autocomplete to fill in `lab7`.

## Step 6: Running the tests

<img width="809" alt="Screenshot 2023-02-26 at 1 01 45 PM" src="https://user-images.githubusercontent.com/25190789/221437062-a271b995-a15d-4285-b5b6-2c0dbaec59fe.png">

The next step is compiling and running the tests, which I accomplished by typing in `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java<enter>` and `java <^v> org.junit.runner.JUnitCore L<tab>T<tab><enter>`. The first command compiles the tests and cannot be made faster besides copy-pasting in the command. I then copied (`<^c`) the `-cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar` portion of the first command, using it in the next command which runs the tests. I autocompleted `ListExamplesTests`.

## Step 7: Fixing the code

<img width="517" alt="Screenshot 2023-02-26 at 1 05 15 PM" src="https://user-images.githubusercontent.com/25190789/221437239-c65bd016-bef3-4d1c-952a-d1718de4fd4f.png">

The next step is fixing the code such that the tests pass, which I accomplished by typing in `sed -i '43 s/1/2/1' L<tab>.j<tab><enter>`. Rather than using `nano`, I chose to directly edit the file using `sed`, as I had already inspected the file and knew exactly where the error was. This is not as applicable in general use, but is useful for this case of trying to complete a known set of tasks as fast as possible. Specifically, the command replaces (the `s`) only the first occurrence (the last `/1`) of `1` (the first `/1`) with `2` (the `/2`) in line 43 (the `43`), fixing the bug. Again, I autocompleted `ListExamples.java`.

## Step 8: Running the tests (again)

<img width="809" alt="Screenshot 2023-02-26 at 1 08 50 PM" src="https://user-images.githubusercontent.com/25190789/221437414-6093cc31-d557-4957-90d5-c9bb14561ec4.png">

The next step is re-running the tests, which I did by typing in `<up x3><enter>` and `<up x3><enter>`. Since the compilation command is 3 up in the command history, I simply accessed it with `<up>` presses. I did the same for the running command.

## Step 9: Committing and pushing the changes

<img width="489" alt="Screenshot 2023-02-26 at 1 11 26 PM" src="https://user-images.githubusercontent.com/25190789/221437551-b4b48531-3872-46ec-8abd-1d7afd904626.png">

The next step is committing and pushing the changes to the repository, which I did by typing in `git add L<tab>.j<tab><enter>`, `git commit -m a<enter>`, and `git push<enter>`. I autocompleted `ListExamples.java`, used a short non-descriptive commit message (bad practice in reality, but fine for this), and finally pushed to the GitHub repository.
