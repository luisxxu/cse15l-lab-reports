# Week 3 Lab Report

## Part 1

**StringServer code:**
    
    String returnString = "";
    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                returnString += parameters[1] + "\n";
            }
            return String.format(returnString);
        }
        return "404 Not Found!";
    }
   
**String Server Screenshots**

<img width="569" alt="Screen Shot 2023-01-29 at 5 23 52 PM" src="https://user-images.githubusercontent.com/114445896/215616590-5e7affc3-3f6b-4f14-b87e-c2109afadc22.png">

>**The method called was handleRequest, and the argument passed through is the URL that's entered with the domain. Once the URL is passed through, the method reads the path and query to see if it matches with add-message and ?s=string. The value of return string, which keeps track of the final output displayed on the website, updates by adding "Good\n" to the string.**

<img width="568" alt="Screen Shot 2023-01-29 at 5 24 48 PM" src="https://user-images.githubusercontent.com/114445896/215616654-8bd41a77-4856-4e15-8ea8-a0facbce63e8.png">

>**The method called was handleRequest, and the argument passed through is the URL that's entered with the domain. Once the URL is passed through, the method reads the path and query to see if it matches with add-message and ?s=string. The value of return string, which keeps track of the final output displayed on the website, updates by adding "Morning\n" to the string.**

## Part 2

**Non-failure inducing input**

    @Test 
    public void testReverseInPlace() {
        int[] input1 = { 3 };
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{ 3 }, input1);
    }
    
**Failure inducing input**

    @Test
    public void testReverseInPlace2() {
      int[] input1 = {1, 2, 3, 4, 5};
      ArrayExamples.reverseInPlace(input1);
      assertArrayEquals(new int[]{ 5, 4, 3, 2, 1}, input1);
    }
    
**Symptom output**

<img width="758" alt="Screen Shot 2023-01-29 at 6 31 58 PM" src="https://user-images.githubusercontent.com/114445896/215618933-3f338706-1dbd-4796-8bf6-1ead0662136d.png">

**Original code (with bug)**

    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = arr[arr.length - i - 1];
        }
        
**Fixed code**        
        
    static void reverseInPlace(int[] arr) {
        int[] newArray = new int[arr.length];

        for(int i = 0; i < arr.length; i += 1) {
          newArray[i] = arr[i];
        }
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = newArray[arr.length - i - 1];
        }
    }

>**The bug in reverseInPlace was that the first half of the array was being correctly changed, but the second half of the array was being changed to the changed first half’s elements since the code uses the same array to reverse. To fix this bug, the code should create a new array and take the elements in reverse order of the original array and add it to the new array.**

## Part 3

I learned how a website handles requests with the use of paths and queries, and how to code methods that can manipulate and use the inputs from a URL. It was really interesting to see the input as the URL name and the output as the display of the website, directly reflecting the changes into the website in real time. I also learned how to run a server on a different machine using ssh, which made me realize how public websites are run. It was cool to learn that servers are actually just computers that are hosting the programs that govern how the website runs.
    
