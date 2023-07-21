# Mortgage Rate Calculator

## Overview

Our goal is to create a program that will calculate the monthly payment and display it as a currency.

The user should be prompted 3 times to input relevant values:

1. Principal
1. Annual Interest Rate
1. Period (in years)

After the user enters these 3 values, the monthly payment should be displayed as a currency.

The formula to calculate monthly mortgage rates is as follows is as follows:

`M = P _ (r _ (1 + r)^n) / ((1 + r)^n - 1)`

- **M** - represents the monthly mortgage payment

- **P** - is the principal amount (loan amount)

- **r** - is the monthly interest rate (annual interest rate divided by 12 and then divided by 100)

- **n** - is the total number of monthly payments (loan period multiplied by 12)

Below is the Java code I wrote as a solution to this problem.

## Solution

```
import java.text.NumberFormat;
import java.util.Scanner;
import java.lang.Math;

public class Main {
    public static void main(String[] args) {
        Scanner scannerObj = new Scanner(System.in);

        System.out.println("principal");
        int principal = Integer.parseInt(scannerObj.nextLine());

        System.out.println("annual interest rate");
        double annualInterestRate = Double.parseDouble(scannerObj.nextLine());

        System.out.println("period in years");
        String periodInYears = scannerObj.nextLine();

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

After finishing I looked at examples of how others implemented this project. I realized that I could have made the code simpler by converting `int principal = Integer.parseInt(scannerObj.nextLine());` to ` int principal = scannerObj.nextInt();`.

I could have also applied something similar to the other inputs. In general, I learned that instead of having to convert between data types, we can 'prime' the scanner to directly read the input as the type of data we want.
