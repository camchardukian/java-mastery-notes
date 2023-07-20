# Monthly Loan Balance Calculator

## Overview

This seems pretty straightforward... It's a loan calculator that calculates your monthly payment as well as how much of the loan balance remains after each month of payments.

## Solution

```
import java.text.NumberFormat;
import java.util.Scanner;
import java.lang.Math;

public class Main {
    public static void main(String[] args) {
        int MONTHS_IN_YEAR = 12;
        int principal = (int) returnNumberFromPrompt("Principal", 10000, 200000);
        float annualInterestRate = (float) returnNumberFromPrompt("Annual Interest Rate", 0, 30);
        int periodInYears = (byte) returnNumberFromPrompt("Period (in years)", 1, 30);

        int totalMonthsToPay = periodInYears * MONTHS_IN_YEAR;

        double monthlyInterestRate = annualInterestRate / MONTHS_IN_YEAR / 100;
        double monthlyPayment = principal * (monthlyInterestRate * Math.pow((1 + monthlyInterestRate), totalMonthsToPay)) / (Math.pow((1 + monthlyInterestRate), totalMonthsToPay) - 1);
        System.out.println("--------------");
        System.out.println("Monthly payment amount: " + NumberFormat.getCurrencyInstance().format(monthlyPayment));
        System.out.println("--------------");
        System.out.println("Remaining balance after each month...");
        printMonthlyLoanBalance(principal, monthlyInterestRate, totalMonthsToPay);
    }


    public static double returnNumberFromPrompt(String prompt, double min, double max) {
        Scanner scannerObj = new Scanner(System.in);
        double value;

        while (true) {
            System.out.println(prompt);
            value = Double.parseDouble(scannerObj.nextLine());
            if (value < min || value > max) {
                System.out.println("Please enter a value between" + min + " and " + max);
                continue;
            }
            break;
        }
        return value;
    }

    public static void printMonthlyLoanBalance( int principal, double monthlyInterestRate, int totalMonthsToPay) {
        double remainingLoanBalance = principal;
        for (int numberOfMonthsPassed = 1; remainingLoanBalance > 0; numberOfMonthsPassed+=1) {
            remainingLoanBalance = principal * (Math.pow(1 + monthlyInterestRate, totalMonthsToPay) - Math.pow((1 + monthlyInterestRate), numberOfMonthsPassed)) / (Math.pow(1 + monthlyInterestRate, totalMonthsToPay) - 1);
            System.out.println("Month " + numberOfMonthsPassed + ": " + NumberFormat.getCurrencyInstance().format(remainingLoanBalance));
            if (remainingLoanBalance <= 0) {
                System.out.println("loan paid off!");
                break;
            }
        }
    }
}
```

## Conclusion

I thought this project was pretty straightforward. One random observation I had while completing this project was how convenient JavaScript makes passing an object as an argument whereas for Java it seemed like I'd have to create a separate class and instantiate an instance of that class.

That seems like a bit of a pain. I get that Java is supposed to be stricter, but even in TypeScript I can pass an object as an argument and declare the types inline (and it's perfectly reasonable to do so if the object is simple).

Maybe I'll learn more about this later as I move toward the OOP sections of these courses, but for now I like the JS/TS approach more, even if I understand Java does have some advantages for stability and large systems.
