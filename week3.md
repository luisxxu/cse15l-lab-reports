code

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
   
pictures

<img width="569" alt="Screen Shot 2023-01-29 at 5 23 52 PM" src="https://user-images.githubusercontent.com/114445896/215616590-5e7affc3-3f6b-4f14-b87e-c2109afadc22.png">
<img width="568" alt="Screen Shot 2023-01-29 at 5 24 48 PM" src="https://user-images.githubusercontent.com/114445896/215616654-8bd41a77-4856-4e15-8ea8-a0facbce63e8.png">

good test

    @Test 
    public void testReverseInPlace() {
        int[] input1 = { 3 };
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{ 3 }, input1);
    }
    
bad test

    @Test
    public void testReverseInPlace2() {
      int[] input1 = {1, 2, 3, 4, 5};
      ArrayExamples.reverseInPlace(input1);
      assertArrayEquals(new int[]{ 5, 4, 3, 2, 1}, input1);
    }
    
Symptom

<img width="758" alt="Screen Shot 2023-01-29 at 6 31 58 PM" src="https://user-images.githubusercontent.com/114445896/215618933-3f338706-1dbd-4796-8bf6-1ead0662136d.png">

    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = arr[arr.length - i - 1];
        }
        
fixed        
        
    static void reverseInPlace(int[] arr) {
        int[] newArray = new int[arr.length];

        for(int i = 0; i < arr.length; i += 1) {
          newArray[i] = arr[i];
        }
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = newArray[arr.length - i - 1];
        }
    }
    
