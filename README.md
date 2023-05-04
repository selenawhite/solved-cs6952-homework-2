Download Link: https://assignmentchef.com/product/solved-cs6952-homework-2
<br>
<h1>1.     Flip Flop: 10 points</h1>

<strong>File: </strong>flip_flop.cpp

We want to model the behavior of a strange sort of fish over some time. On seconds divisible by <em>a </em>it flips, on those divisible by <em>b </em>it flops and on those divisible by both it flips and flops. To simulate this behavior your program should print “flip” when it flips, “flop” when it flops and “flipflop” when it flips and flops. If the fish doesn’t do any action then you should just print out the current second.

Input to your program for each case will be the second to start at, the number of seconds to simulate and the values for <em>a </em>and <em>b</em>. Your program should then log the behavior of the fish by printing its action or the current time as specified above for the desired number of seconds. Note that 0 counts as divisible by any number, recall that 0 % x is always 0 for any value of x.

<h2>Example Input</h2>

3

0 16 3 5

10 10 2 7 4 20 12 4

<strong>Expected Output </strong>Case 0: flipflop 1 2 flip 4 flop flip 7 8 flip flop 11 flip 13 14 flipflop Case 1: flip 11 flip 13 flipflop 15 flip 17 flip 19 Case 2: flop 5 6 7 flop 9

10 11 flipflop 13 14 15 flop

17 18 19 flop 21 22 23

<h1>2.     Worth Every Penny: 30 points</h1>

<strong>File: </strong>worth_every_penny.cpp

You are running a business of selling stainless-steel wedding rings. Bill, the software engineer you hired to program your business software is an experienced programmer, so he decided to use double-precision floating-point numbers (double) for all amounts of money in the software, fearing that one day a puny float would run out of precision to represent your billion-dollar fortune. Being a brilliant businessman yourself, you have come up with a unique pricing strategy: the first ring is sold for 25 cents ($0.25), the second one for $10.25, the third one $20.25 and so on. In other words, the price for each ring is $10 more than the last. This plan has proven to work quite well: over the years you have sold 30’000’000 (thirty million) rings, and every penny earned was recorded in the software. The profit from selling all these rings is $4499999857500000. This result can be verified using, for example, <a href="https://www.wolframalpha.com/">Wolfram Alpha</a><a href="https://www.wolframalpha.com/">.</a> See the following screenshot for how to use Wolfram Alpha to evaluate this number.

Yet the software written by Bill surprisingly reports a different profit value. Obviously you are not happy and decide to take the matters into your own hands.

In this problem you will write a program to compute the exact total profit after the <em>n − </em>1th ring is sold. <em>n </em>will be given to your program as input, and it will be an integer between 1 and 30000000, inclusively. For example, if <em>n </em>= 3, the profit should be 0<em>.</em>25+10<em>.</em>25+20<em>.</em>25 = 30<em>.</em>75. In addition to the exact total profit, your program should also output the number computed by Bill’s program (remember that he used double-precision floating-point numbers for all his calculations). Print your output in dollars, in fixed point notation, to up to 2 digits after the decimal point. You can use std::fixed and std::setprecision in the &lt;iomanip&gt; header file. For example, to output the variable num in fixed point notation, to 2 digits of accuracy after the decimal point, do as follows: std::cout &lt;&lt; std::fixed &lt;&lt; std::setprecision(2) &lt;&lt; num &lt;&lt; “
”;

Please note that each ring is sold independently, so the program needs to add the rings’ prices to the sum (profit) one by one. In other words, you <strong>cannot use</strong>

Figure 1: Evaluating sums using Wolfram Alpha

<strong>a closed-form formula </strong>such as the one shown in the Wolfram Alpha picture. You need to write a loop to compute the total profit.

<h2>Example input</h2>

5 1

100

4000

200000

30000000

<h2>Example output</h2>

Case 0:

1 rings were sold

Bill’s program outputs 0.25 The exact profit is              0.25 Case 1:

100 rings were sold

Bill’s program outputs 49525.00

The exact profit is               49525.00 Case 2:

4000 rings were sold

Bill’s program outputs 79981000.00 The exact profit is              79981000.00 Case 3:

200000 rings were sold

Bill’s program outputs 199999050000.00 The exact profit is     199999050000.00 Case 4:

30000000 rings were sold

Bill’s program outputs 4499999855305422.00

The exact profit is                       4499999857500000.00

Hint: you will need to use a type with enough precision to compute the exact profit. Below is a list of numeric types and their most common sizes in practice that we have discussed so far (unsigned types have been omitted to keep the table compact).

<table width="187">

 <tbody>

  <tr>

   <td width="69">types</td>

   <td width="55">size</td>

   <td width="63">#include</td>

  </tr>

  <tr>

   <td width="69">char</td>

   <td width="55">8 bits</td>

   <td width="63">none</td>

  </tr>

  <tr>

   <td width="69">int8_t</td>

   <td width="55">8 bits</td>

   <td width="63">&lt;cstdint&gt;</td>

  </tr>

  <tr>

   <td width="69">short</td>

   <td width="55">16 bits</td>

   <td width="63">none</td>

  </tr>

  <tr>

   <td width="69">int16_t</td>

   <td width="55">16 bits</td>

   <td width="63">&lt;cstdint&gt;</td>

  </tr>

  <tr>

   <td width="69">int</td>

   <td width="55">32 bits</td>

   <td width="63">none</td>

  </tr>

  <tr>

   <td width="69">int32_t</td>

   <td width="55">32 bits</td>

   <td width="63">&lt;cstdint&gt;</td>

  </tr>

  <tr>

   <td width="69">long</td>

   <td width="55">32 bits</td>

   <td width="63">none</td>

  </tr>

  <tr>

   <td width="69">float</td>

   <td width="55">32 bits</td>

   <td width="63">none</td>

  </tr>

  <tr>

   <td width="69">long long</td>

   <td width="55">64 bits</td>

   <td width="63">none</td>

  </tr>

  <tr>

   <td width="69">int64_t</td>

   <td width="55">64 bits</td>

   <td width="63">&lt;cstdint&gt;</td>

  </tr>

  <tr>

   <td width="69">double</td>

   <td width="55">64 bits</td>

   <td width="63">none</td>

  </tr>

 </tbody>

</table>

<h1>3.     Estimating <em>π </em>using Leibniz’s formula: 20 points</h1>

<strong>File: </strong>leibniz.cpp

The German mathematican Leibniz (1646 – 1716) discovered the following formula to approximate <em>π</em>:

<em>π/</em>4 = 1 <em>− </em>1<em>/</em>3 + 1<em>/</em>5 <em>− </em>1<em>/</em>7 + 1<em>/</em>9 <em>− </em>1<em>/</em>11 + <em>…</em>

Write a program to compute an approximation of <em>π </em>using the first <em>n </em>terms in Leibniz’s series, where 1 <em>≤ n ≤ </em>10000000 is input. Print your output in fixed-point notation, to up to 8 digits of accuracy. You can use std::fixed and std::setprecision from the &lt;iomanip&gt; header file. For example, to output the variable num in fixed point notation, to 4 digits of accuracy after the decimal point, do as follows: std::cout &lt;&lt; std::fixed &lt;&lt; std::setprecision(4) &lt;&lt; num &lt;&lt; “
”;.

<h2>Example input</h2>

6 1

100

1000

10000

100000

1000000

<h2>Example output</h2>

Case 0:

Pi estimated as: 4.00000000 Case 1:

Pi estimated as: 3.13159290 Case 2:

Pi estimated as: 3.14059265 Case 3:

Pi estimated as: 3.14149265 Case 4:

Pi estimated as: 3.14158265 Case 5:

Pi estimated as: 3.14159165

<h1>4.     Root Finding: 40 points</h1>

<strong>File: </strong>root_finding.cpp

This assignment is to use Newton’s method to find the roots of an equation, starting the search at some point and finding the root to some desired accuracy or number of iterations. The equation you will be computing roots of is:

<em>x</em><sup>5 </sup>+ 6<em>x</em><sup>4 </sup>+ 3<em>x</em><sup>3</sup><em>− x − </em>50                                                      (1)

Newton’s method works by starting from some (hopefully close) guess of the root and then iteratively updating it until we get close enough to the actual root of the equation. In other words, you iteratively compute the next best guess for the root using the following formula until convergence:

<em>f</em>(<em>x<sub>n</sub></em>)

<em>x</em><em>n</em>+1 = <em>x</em><em>n− f</em><em>0</em>(<em>x</em><em>n</em>)                                                     (2)

Your program doesn’t need to compute <em>f<sup>0</sup></em>(<em>x</em>), instead compute the derivative by hand (or using WolframAlpha or however you prefer) and write the expression in your program. You can test for convergence by checking if <em>x<sub>n</sub></em><sub>+1 </sub><em>≈ x<sub>n</sub></em>, specifically you should stop the root finding when the relative error has reached some threshold:

<em>x</em><em><sup>n</sup></em><sup>+1</sup><em>− x<sup>n</sup></em> <em>≤ ε                                                    </em>(3)

<em>x</em><em>n</em>+1

or you’ve executed <em>n </em>iterations of the root finding method. You can find more information about Newton’s method on <a href="https://en.wikipedia.org/wiki/Newton's_method">Wikipedia</a><a href="https://en.wikipedia.org/wiki/Newton's_method">.</a>

For computing absolute values, sine, cosine and powers you’ll want to use some of the functions in the cmath header (#include &lt;cmath&gt;), documented <a href="http://en.cppreference.com/w/cpp/header/cmath">here</a><a href="http://en.cppreference.com/w/cpp/header/cmath">.</a>

The input to your program for each case will be the <em>x </em>value to start the search at followed by the number of iterations <em>n </em>and the tolerance <em>ε</em>. Your program should then find the root of equation (1) starting the search at <em>x </em>until the root is found to the desired tolerance or you’ve run the maximum number of iterations. When your program has found the root to within the desired precision or run out of iterations you should print:

root at x = A with error E after C iterations

Where A is the root value you found, E is the remaining relative error and C is the number of iterations you took to find the root. Your program will need to run for at least one iteration to find the error between the guess and where we think the root is, even if the guess is exactly on.

<h2>Example Input</h2>

6

-5.2 100 1e-10

-1.0 100 1e-6

-5 1000 1e-10

1 10 1e-4

-7 100 1e-7

1 5 1e-10

<strong>Expected Output </strong>Case 0:

root at x = -5.39065 with error 7.24956e-14 after 5 iterations Case 1:

root at x = -5.39065 with error 2.08036e-09 after 5 iterations Case 2:

root at x = -5.39065 with error 5.60193e-15 after 6 iterations Case 3:

root at x = 1.52641 with error 9.20928e-07 after 6 iterations Case 4:

root at x = -5.39065 with error 5.6942e-13 after 7 iterations Case 5: root at x = 1.52641 with error 0.000774228 after 5 iterations