java c
DEPARTMENT OF MATHEMATICAL SCIENCES
AUTUMN SEMESTER 2024-2025
MATH1109 - CORE MATHEMATICS
Python Coursework
Deadline: 15:00, Wednesday 27/11/2024
Rules
It is not permitted to use generative artificial intelligence (AI) software for this coursework. Ensure that you have read and have understood the Policy on academic misconduct. One of the things stated in this policy is that “The submission of work that is generated and/or improved by software that is not permitted for that assessment, for the purpose of gaining marks will be regarded as false authorship and seen as an attempt to gain an unpermitted academic advantage”.
You are allowed to work together and discuss in small groups (two to four MATH1109 students) but you must write all code by yourself with the exception that you may copy from material provided on the MATH1109 Moodle page.
You may ask for and receive help from the tutor Richard Rankin although not all questions will be answered and those that are will be answered to all students in the class.
Each student is to submit their own coursework.
You must submit one .py file for each question. A full submission contains three Python files:
• legendre.py,
• square_root.py,
• time_steppers.py.
You are strongly encouraged to use the Spyder IDE (integrated development environment).
Marks breakdown
This coursework is out of 100 marks:
• Q1 – 40 marks.
• Q2 – 30 marks.
• Q3 – 30 marks.
Guidelines
For full output data marks, your functions need to return the correct outputs for the particular input arguments.
For full plot marks, your plot(s) should have the correct data plotted, axis labels, a legend if appropriate, and a descriptive title. Note that you will not be penalised for not using TeX/LaTeX fonts.
You should comment your code as discussed in Appendix 3 of the Python Notes and all functions should have a docstring, see Chapter 7.6 of the Python Notes. Some marks will be assigned for commenting and docstrings.
Please be aware that we will test your functions with an automated marker to check that they work and produce the desired output(s), both with the data given in the templates and with different undisclosed data.
.py files that include template functions can be found in the same folder as this file on the MATH1109 Moodle page.
The template .py files also contain some simple tests of your functions. You are encouraged to write your own tests of your functions in a separate file.
If your modules have filenames that differ to what has been explicitly asked for, then your modules will not run through the automarker, and you risk scoring low output/plot marks.
The automated tests for all questions will be “timed out” if they take too long to run. All questions should only need at most a few seconds to run.
When setting up a figure inside a function, you should first use the following syntax before plotting anything:
fig = plt.figure()
fig can then be returned from the function as if it were any other variable.
Questions
1.   The   Legendre   polynomials   {Lu   (x)}u≥0   are   a   set   of   polynomials   that   are   orthogonal   over   the   interval   (−1,   1).   This   means that

The   Legendre   polynomials can   be constructed using the recurrence   relationship:
L0   (x) =   1,
L1   (x) = x,
nLu   (x) = (2n − 1)xLu−1   (x) − (n − 1)Lu−2   (x),       for   n   ≥ 2.
Your   task:
(a)      Complete the function found in legendre.py (available on   Moodle) with   prototype:
def      compute   _   legendre (x,p)
•   This   function   should   compute   the   Legendre   polynomials   up   to   and   including   degree   p   at   the   points contained   in   x.
•   This   function   should   take   as   input:
–   A   one-dimensional   numpy.ndarray   x   -   the   values   at   which   to   evaluate   the Legendre polynomials;
–   An   int p - the maximum polynomial   degree to   evaluate;
•   The   function   should   output:
–   A numpy.ndarray of shape   (p+1,len(x)) - the evaluated Legendre polynomials.
Once you   have written   compute_legendre(), test   it   by   running legendre.py.   You should obtain the   following:
Legendre      polynomials:
[[ 1. 1. 1. 1. 1. ]
[-1. -0.5 0. 0.5 1. ]
[ 1. -0.125 -0.5 -0.125 1. ]
[-1. 0.4375 -0. -0.4375 1. ]]


(b)      Complete the function found in legendre.py with prototype:
def    plot   _   legendre (p)
•   This   function   should   plot   the   Legendre   polynomials   up   to   and   including   degree   p   over   the   interval [−1,   1] on a single   set   of axes.
•   This   function   should   take   as   input:
–   An   int p - the maximum   polynomial degree to   plot;
•   The   function   should   output:
–   A matplotlib.figure   .Figure - a handle to the plot created.
Once you have written plot_legendre(), test it by   running legendre.py.






[40   marks]
2.    In   this   question, you   will   implement   an   algorithm   to   find   an   approximate   square   root   of   a   > 0.   The   mathematical square   root function   has the following Taylor expansion about a代 写MATH1109 - CORE MATHEMATICS AUTUMN SEMESTER 2024-2025Python
代做程序编程语言   point x2:

This motivates the following   iteration

where   N   is   some   positive   integer.
The   iteration   should   begin   with   an   initial   guess      is   considered   sufficiently   accurate   when


for   some   give   error   tolerance   ε   .
Your   task:
Complete the function found in square_root.py (available on   Moodle) with the   prototype:
def    approx   _   square   _root (a,N,x0 ,   eps)
•   This   function   should   apply   (1) to   find   the   approximate   square   root   of   a.
•   This   function   should   take   as   input:
–   A float a - the value to   be   square   rooted;
–   An   int N - to control how   many terms   in the   Taylor   expansion   are   used;
–   A float eps - the tolerance at which to stop   the   iteration;
–   A float x0 - the initial   guess for the   iteration.
•   The   function   should   output   (in   this   order):
–   A float - the (approximate) positive value   of the square   root   of a;
–   An   int - the number of iterations required to   obtain   a   sufficiently   accurate   approximation.
Once you have written approx_square_root(), test it by running square_root   .py.   You should obtain the   following:
sqrt(25) = 5.0 , No_iterations = 4
sqrt(10) = 3.162277660168379 , No_iterations = 2
Note:   Very tiny changes to these values   are   acceptable   due to   the   way   Python   carries   out   floating   point   arithmetic.

[30   marks]


3.      Suppose   we   wish   to   solve   the   scalar   initial   value   problem

A two-point method for approximating solutions to this problem   has   the   time   stepping   formulae:yu+2   =   yu+1   + δt(3f(tu+1   ,   yu+1) −   f(tu,   yu))/2,         n = 0, …   ,   N −   2                                                                (4)where,   δt = T/N and   tu    = nδt,   n   = 0, …   ,   N.In   order   to   findy2   , both   y0   andy1   are   required.   y0    is   available   from   the   initial   condition,   but   in   general, y1 is   not   known.   y1   can   be   simply   provided, as   in   part   (a), or   calculated   some   other   way,   as   in   part   (b).Your   task:(a)    Complete the function found in time_steppers.py (available on Moodle) with   the   prototype:def    perform   _time   _   stepping1 (T,N,y0 ,y1 ,   f)•   This   function   should   use   the   method   shown   in   (4) to   approximately   solve   the   IVP   (2)-(3).•   This   function   should   take   as   input:–   A float T - the final time   T;–   An   int   N   - the   number   of   time-steps   to   perform;–   A float y0 - the   initial value y0;–   A   float   y1 - the   value   to   use   for   y1;–      a function f - the function f(t,   y).•   The   function   should   output   (in   this   order):–      a   numpy.ndarray   - a   vector   containing   all   the   time   points   {tn}Nn=0;–      a   numpy.ndarray   - a   vector   containing   all   the   approximations   {yn}Nn=0.Once   you have   written   perform_time_stepping1()   test it by running time_steppers   .py. You should   obtain the following:   perform_time_stepping1:tn      =            [0   .          0   .5    1   .            1   .5    2   .          2   .5      3   .          3   .5    4   .          4   .5    5   .    ]yn    =             [1   .                                                    1   .23606798    1   .44647817      1   .6412379             1   .82300795    1   .99402943   2.15596995    2.31011529    2.45747855    2.59887356    2.73496507](b)    Complete the function found in time_steppers.py (available on Moodle) with   the   prototype:   def    perform   _time   _   stepping2 (T,N,M,y0 ,   f)•   This   function   should   use   the   method   shown   in   (4) to   approximately   solve   the   IVP   (2)-(3).•   To   find   a   value   for   y1    ≈   y(δt), M   steps   of   the   forward   Euler   method   should   be   used.•   This   function   should   take   as   input:–   A float T - the final time   T;–   An   int   N   - the   number   of   time-steps   of   (4)   to   perform;–   An   int   M   - the   number   of   time-steps   of   forward   Euler   to   perform   to   findy1;–   A float y0 - the   initial value y0;–      a function f - the function f(t,   y).•   The   function   should   output   (in   this   order):–      a   numpy.ndarray   - a   vector   containing   all   the   time   points   {tn}Nn=0;–      a   numpy.ndarray   - a   vector   containing   all   the   approximations   {yn}Nn=0   .Once   you have   written   perform_time_stepping2()   test it by running time_steppers   .py. You should   obtain the following:perform_time_stepping2:   tn      =            [0   .          0   .5    1   .            1   .5    2   .          2   .5      3   .          3   .5    4   .          4   .5    5   .    ]yn    =             [1   .                                                    1   .23861555    1   .44864405      1   .64325985      1   .82490307      1   .99581873   2.15766904    2.31173637    2.45903135    2.60036596    2.73640354]

[30   marks]
   
   
   





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
