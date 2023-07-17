# Mortgage Rate Calculator With Error Handling

## Overview

We're looking to improve upon our previous mortgage rate calculator by informing users when they've entered an invalid value and reprompting them to instead add a valid value.

## Solution

```
import java.text.NumberFormat;
import java.util.Scanner;
import java.lang.Math;

public class Main {
    public static void main(String[] args) {
        Scanner scannerObj = new Scanner(System.in);
        int principal = 0;
        System.out.println("principal");
        while (true) {
            principal = Integer.parseInt(scannerObj.nextLine());
            if (principal <= 1000 || principal >= 1_000_000) {
                System.out.println("please enter a principal value greater than 1,000 and less than 1,000,000");
                continue;
            }
            break;
        }
        System.out.println("annual interest rate");
        double annualInterestRate;
        while (true) {
            annualInterestRate = Double.parseDouble(scannerObj.nextLine());
            if (annualInterestRate <= 0 || annualInterestRate >= 30) {
                System.out.println("please enter an annual interest rate greater than 0 and less than 30");
                continue;
            }
            break;
        }
        System.out.println("period in years");
        String periodInYears;
        while (true) {
            periodInYears = scannerObj.nextLine();
            if (Integer.parseInt(periodInYears) < 1 || Integer.parseInt(periodInYears) > 30) {
                System.out.println("please enter a value from 1-30");
                continue;
            }
            break;
        }

        int totalMonthsToPay = Integer.parseInt(periodInYears) * 12;

        double monthlyInterestRate = annualInterestRate / 12 / 100;
        double monthlyMortgagePayment = principal * (monthlyInterestRate * Math.pow((1 + monthlyInterestRate), totalMonthsToPay)) / (Math.pow((1 + monthlyInterestRate), totalMonthsToPay) - 1);

        NumberFormat currency = NumberFormat.getCurrencyInstance();
        String result = currency.format(monthlyMortgagePayment);
        System.out.println("monthly mortgage payment is:" + result);
    }
}
```

## Conclusion

I think my general implementation of this project was solid, but I could've made the code more readable by taking additional time to refactor it.

I could've improved the code by making a reusuable function for the looping and error handling to better help the program adhere to the DRY principle.
