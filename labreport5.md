# Lab Report 5

## How could the tasks in Lab Report 4 been completed using a bash script?

Each command for the tasks could all be put into a bash script and would've completed the tasks incredibly fast. To create this bash file, we have to use the touch command and nano command to edit this file.

```
touch taskrunner.sh
nano taskrunner.sh
```
Now that we're located inside a bash file, we can go through the tasks and write commands in the bash script for these lines.
#

First, we need to log into the SSH server, so our first command should SSH into the server.
```
ssh cs15lwi23apa@ieng6.ucsd.edu

```
To start the tasks, we need to clone the lab7 repository, so we have to write a git clone command, then enter the directory that we just cloned. 
```
git clone git@github.com:luisxxu/lab7.git
cd lab7
```

Now that we're located inside the directory, we have to run the tasks. We have to write a javac and java command to run the JUnit tests to prove that there's an error within the code.
```
javac -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar".java
java -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples
```

At this point, we'll see that there's an error with the merge function in ListExamples. We already know the error in ListExamples, which is when a variable in a while loop should be "index2" instead of "index1". We don't have to enter the specific file, we can just echo the entire code with the fixed code and use output redirection to overwrite the ListExamples.java file. 
```
echo 'import java.util.ArrayList;

import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }


}' > ListExamples.java
```

Now that we've fixed the code, we can use the same java and javac commands as before to run the JUnit tests to prove that the error was fixed and all tests should pass.
```
javac -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar".java
java -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples
```

After proving that the tests all run correctly and the code is working properly, we just have to do git add, git commit, and git push to commit changes to the git repository.
```
git add ListExamples.java
git commit -m "updated"
git push
```

Once we have all these commands written, we can run the bash file using this command:
```
bash taskrunner.sh
```
Our tasks should all run now and complete the tasks as outlined in the lab!
