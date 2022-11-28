# Lab Report 5

## Autograder

```
# Create your grading script here
set -e
rm -rf student-submission
git clone $1 student-submission
cd student-submission

set -e
if [[ -e ListExamples.java ]]
then
    echo "file found"
else
    echo "file not found, check formatting or naming"
    exit 1
fi
set +e
javac -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" *.java 2> stderr.txt

if [[ $? -ne 0 ]]
then
    echo "compiler error"
    cat stderr.txt
    exit 1
else
    echo "successfully compiled"
fi

java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples > output.txt
grep "Tests run:" < output.txt > results.txt
PASSED=`wc -l results.txt | grep -o '[0-9]'`
VARS=(`grep -Eo '[0-9]{1,2}' < results.txt`)

if [[ ${VARS[0]} -ne ${VARS[1]} ]]
then
    echo "error"
    echo "$((${VARS[0]}-${VARS[1]}))/7 tests passed."
else
    echo "All tests passed."
fi
cat output.txt
```

## Screenshots

1. Correct Repository (#2)

![correct](https://cdn.discordapp.com/attachments/1023749314587140137/1046733563783020574/image.png)

2. Compiler Error Repository (#3)
   ![compiler err](https://cdn.discordapp.com/attachments/1023749314587140137/1046755469517131827/image.png)

3. FileName Error Repository (#6)

![filename](https://cdn.discordapp.com/attachments/1023749314587140137/1046749195786264636/image.png)

## Tracing Tests: FileName Error repository

```
set -e
rm -rf student-submission
git clone $1 student-submission
cd student-submission
```

`set -e` allows for the code to immediately exit, while the next three lines, respectively:

1. `rm -rf student-submission`

This allows for a recursive removal of all files that were run using this code last.

2. `git clone $1 student submission`

This clones the GitHub repository that the user chose, which in this case is `https://github.com/ucsd-cse15l-f22/list-methods-corrected`

3. `cd student-submission`

This changes the directory into the `student-submission` folder inside the repository

Since all lines are successful, there is no standard output or error, so it would return error code 0.

```
set -e
if [[ -e ListExamples.java ]]
then
    echo "file found"
else
    echo "file not found, check formatting or naming"
    exit 1
fi

```

These lines check if ListExamples.java is in the repository, and if it isn't, then it will throw error code 1. Since it is not found, then the then statement line does not run, therefore printing out error code 1, along with a statement that tells the user to check their file, as their file could have problems with formatting or naming.

Everything past this line of code does not run, as the code exits early because of exit code 1.
