# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

I used the lecture slides/video on sorting, quicksort to look at slide 34 to review the material and compare my answer. Ali Torabi showed me a link https://walkccc.me/CLRS/Chap07/Problems/7-5/ to understand the math side of this and helped me. I went to his office hours where I learned I did not show all the right possibilities which I then fixed. 

I submitted this work Fall 2024.

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

When choosing 3 random elements, the array is essentially split into 3 parts, left, middle, and right. The middle includes the best pivots which is about 1/2 of the array, and the left and right sides are each 1/4 probabilty of holding the pivot. While looking at this, let's look at the $3^3$ = 27 possibilities.
1. Elements are chosen left, middle, right = $(1/4) * (1/2) * (1/4)$ = $(1/32)$
   a.) Six ways it can switch around (LMR, MLR, LRM, MRL, RML, RLM) so $(1/32) * 6 = 6/32 = 12/64$
2. Elements are chosen left, middle, middle = $(1/4) * (1/2) * (1/2) = 1/16 $
   a.) Three ways it can switch around (LMM, MLM, MML) so $(1/16) * 3 = 3/16 = 12/64$
3. Elements are chosen middle, middle, middle = $(1/2) * (1/2) * (1/2)$ = $(1/8)$
   a.) One way it can switch around (MMM) so $(1/8) = 8/64$
4. Elements are chosen middle, middle, right = $(1/2) * (1/2) * (1/4) = 1/16 $
   a.) Three ways it can switch around (MMR, MRM, RMM) so $(1/16) * 3 = 3/16 = 12/64$

So, 
$(12/64) + (12/64) + (8/64) + (12/64)  = 44/64$ 

In percentage form this would be around $68.75%$. So, the percentage of finding a good pivot value is 68.75%, which is a greater probability than choosing the first value.


With the middle being a half and being the best case pivot value, this increases the odds of finding a good pivot. 
