# Financial Calculators

 * CAGR Calculator
 * Input Stream CAGR Calculator
 * Net Increase Calculator
 * Retirement Calculator

### Required

All programs require python3 to run.

### CAGR Calculator

CAGR, or Compounding Annual Growth Rate, is a way to measure how fast
a contribution has compounded over a given time. For instance, if you
start with 10,000 of something (money, mice, self-replicating robots,
etc.), and that quantity becomes 20,000 over 10 periods, then the quantity
grew by 7.18% per period. Compounding growth is very powerful!

Usage:

```bash
$ ./cagr.py <Beginning Value> <Ending Value> <Number of Periods>
```

This program works based on the following equation:

(ending\_value / begginning\_value)^(1 / number\_of\_periods) - 1

### Input Stream Cagr

CAGR is simple enough. However, what if you started with 10,000 of something,
then added an additional amount per year (say 1,000 more). This happens a lot
with money and retirement accounts. CAGR then becomes much more difficult to
determine. This program will estimate the average yearly return with a high
degree of accuracy for such accounts. It should be accurate to +/- 0.01% for
most usage cases.

Usage:

```bash
$ ./inputstreamcagr.py <Beginning Value> <Ending Value> <Contribution per period> <Number of Periods>
```

### Net Increase Calculator

Calculates the multiple of increase given a compounding rate and number of
periods. For instance, if something compounds at a rate of 7% per period for
40 periods, it will increase a total of 14.97 times.

Usage:
```bash
$ ./net_increase.py <Rate of Increase> <Periods>
```

### Retirement Calculator

This program is an compounding calculator / retirement calculator. It takes in
a lot of variables described below. It's built with sensible defaults, but all
parameters can be tweaked as desired.

To run it (with defaults):

```bash
$ ./retirement.py
```

Optional arguments:
```
    -h show this help
    -s starting contribution (defaults to 0)
    -i (float >= 1.00) inflation rate (defaults to 1.03)
    -o (float >= 1.00) compounding rate (defaults to 1.10)
    -c yearly contribution (defaults to 10,000)
    -n years of contribution (defaults to 40)
    -r years till retirement (defaults to 40)
    -m show how much your investments multiply over each of
       [num] periods of time over your investment (off by default)
```

###### Output:
```

Assuming:
        A starting contribution of $0
        An inflation rate of 1.03 (3.00%)
        A compounding rate of 1.1 (10.00%)
        A yearly contribution of $10,000
        40 years of contribution
        and 40 years till retirement

    You'll have a net compounding rate of 1.07 (7.00%)


You will put in a total of $400,000.00
You will retire with the equivalent of $1,996,351.12 in today's currency

```

##### Run the calculator with some options:

* A starting contribution of $50,000
* The default inflation rate of 1.03 (no option given)
* An compounding rate of 1.08 (8%)
* A yearly contribution of $10,000 (same as the default, but specified in the arguments)
* 15 years of contribution
* and 30 years till retirement

While showing how much your money multiplies by if you invest it
at (4) different periods in time over your 15 years of contribution.

```bash
$ ./retirement.py -s 50000 -o 8% -c 10000 -n 15 -r 30 -m 4
```
###### Output:
```
Assuming:
        A starting contribution of $50,000
        An inflation rate of 1.03 (3.00%)
        A compounding rate of 1.08 (8.00%)
        A yearly contribution of $10,000
        15 years of contribution
        and 30 years till retirement

    You'll have a net compounding rate of 1.05 (5.00%)


You will put in a total of $200,000.00
You will retire with the equivalent of $664,699.96 in today's currency

Your money will multiply by:
    4.32 times if you invest it  0 years after the start of your retirement savings
    3.39 times if you invest it  5 years after the start of your retirement savings
    2.65 times if you invest it 10 years after the start of your retirement savings
    2.08 times if you invest it 15 years after the start of your retirement savings

```

##### Disclaimers
This program is not well hardened against improper input.

It has also not been well tested. It seems reliable enough to me, but I make
no promises. Definitely double check these values before using them to make
important life decisions.
