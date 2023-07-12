# Numeric Operations & Manipulations

## Arithmetic

In Java when you divide a whole number by a whole number you get a whole number. For example, if you do `10 / 3`, you’ll get a result of `3`.

If we wanted to get a floating number we would have to rewrite the code to be something like this:
`float result = (float)10 / (float)3;

`

## Casting

In Java there is both implicit and explicit casting. Implicit acting is performed internally by the Java compiler when a smaller data type is assigned to a larger data type.

Explicit casting is needed when converting a larger data type to smaller data type, requires a manual casting operation, and may result in truncation or the loss of data precision.

## Formatting Numbers

Java has a `NumberFormat` class we can use to format numbers.

For example, to format dollars we could write code like this:

```
NumberFormat currency = NumberFormat.getCurrencyInstance()
String result = currency.format(1234567.89)
System.out.println(result)
```

We would then get this output:

> $1,234,567.89

We can also use other method on the `NumberFormat` class to work with percents and perform other operations.
