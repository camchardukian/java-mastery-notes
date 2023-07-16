# Fizzbuzz

## Overview

We've all heard of some variation of the [fizzbuzz problem](https://www.geeksforgeeks.org/fizz-buzz-implementation/).

In this example, we're solving a variation of the fizzbuzz problem that will log "fizz" if the number is divisible by 3, "buzz" if the number is divisible by 5, and "fizzbuzz" if it's divisible by both.

## Solution

```
public class Main {
    public static void main(String[] args) {
        int number = 2;
        String myString = "";
      if (number%3 == 0) {
          myString = "fizz";
      }
      if (number%5 == 0) {
          myString = myString + "buzz";
      }
      String output = myString != null && !myString.isEmpty() ? myString : Integer.toString(number);
      System.out.println(output);
    }
}
```

## Conclusion

I think my solution was decent enough, but I could've improved it by using a scanner object so that the user could've input a number into the program rather than just manually changing `number` inside the code each time I ran the program to test it.
