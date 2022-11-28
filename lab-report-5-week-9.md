# Lab Report 5
For Lab Report 5, we worked to create an autograding script to grade for a set of list method submissions.
```
# Create your grading script here

rm -rf student-submission
git clone $1 student-submission
cp TestListExamples.java student-submission
cd student-submission

if [[ ! -f ListExamples.java ]]
then
    echo "The file ListExamples.java was not found; score is 0."
    exit 0
fi

javac ListExamples.java 2> error.txt
EXIT=$?

javac -cp .:../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar TestListExamples.java

if [[ $(grep -c "^OK" test.txt) -eq 1 ]]
then
    totalNumTests=$(grep -Po "\d+ test" error.txt | grep -Po "\d+")
    echo "All tests passed; score is ${totalNumTests}/${totalNumTests}."
else
    totalNumTests=$(grep -Po "Tests run: \d+" error.txt | grep -Po "\d+")
    testsFailed=$(grep -Po "Failures: \d+" error.txt | grep -Po "\d+")
    testsPassed=$((totalNumTests - testsFailed))
    echo "This submission passed ${testsPassed} out of ${totalNumTests} tests; score is ${testsPassed}/${totalNumTests}."
fi
```

For the first example, I used https://github.com/ucsd-cse15l-f22/list-methods-lab3. Here is the output I received:




For the second example, I used https://github.com/ucsd-cse15l-f22/list-methods-corrected. Here is the output I received:




For the third example, I used https://github.com/ucsd-cse15l-f22/list-methods-filename. Here is the output I received:

