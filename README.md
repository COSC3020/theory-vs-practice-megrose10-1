# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Add your answers to this markdown file.
Part 1:
1.	This can happen if the system runs low on physical memory(RAM). When that occurs, the system uses paging to swap memory between RAM and disk storage, this process is known as virtual memory. Virtual memory allows the program to share memory across different memory locations to ensure it has enough space to run. While using only RAM can be fast, when memory is low and swapping between RAM and disk is required, it introduces latency(lagging), causing the program to run slower than asymptotic analysis predicts. For example, if only your program is running, the analysis will closely predict runtime. However, if multiple programs are running and memory becomes contrained the system may switch to virtual memory, causing delays and make the actual runtime differ from the analysis. While swapping might seem to just add a constant in some situations, the amount of data that needs to be swapped and the frequency of paging can significantly increase the time required, resulting in asymptotic analysis being misleading. 
2. Within asymptotic complexity, we find the fastest growing element, and usually ignore low growing and constant factors. While this may work for many data sets, as the data increases, the runtime can be more than the asymptotic complexity rounded to. Since this is theoretically true, in practice, we cannot always ignore constant factors since they still do contribute to the runtime, even if at a small volume.
3. Depending on the machines the code runs on, the same code can vary in time. Asymptotic analysis does not take in external variables.

Part 2:
Within binary trees, they usually have a complexity of log2(n). So, to find the estimated runtime we can find this by inputting our values. For 1000 elements the runtime is estimated at log2(1000) = 9.9 seconds. For 10000 elements, the runtime is estimated at log2(10000) = 13.3 seconds. This is just an estimation. To see how the logarithmic graph grows to these two points, we can divide them to see how much they grow, (13.3/9.9) = 1.34. So, now taking into account the runtime we are given for 1000 elements which is 5 seconds, we can multiply our rate that goes from 1000 to 10000 by the number resulting in 5 * 1.34 = 6.7 seconds. 

Part 3:
1. One reason is the cache. With larger data sets, cache misses are more frequent. When the cache fills up, data is moved to slower memory, and the program may struggle to find it, leading to slower performance. While this can happen with smaller data sets, it’s more common with larger ones due to the increased likelihood of filling the cache.
2. Depending on the implementation, if the code is very very ineffcient, the time can become much larger. 
3. An unbalanced binary tree can cause performance issues as the data set grows. While smaller data sets may see minimal runtime differences, larger ones can significantly impact performance. Asymptotic analysis can be misleading, as it may not account for the effects of inserting large data into an unbalanced tree. Worst case could even be a binary tree that is so unbalaced it resembles a linked list, and if the result is at the bottom, this can definitely cause runtime errors. The worst runtime you could expect is if it had to go through every node, which would be O(n). The runtime would be O(10000), which may account for why in the example it took 100 seconds.

Citations:
I used lecture notes and slides to base my answers on. I wasn't fully sure if my formula was correct so I tried to search online to see what a binary search tree formula would be but resulted in trying to put log base 1000 in the calculator to check if the formula was right. I worked with Olivia, Ashlyn, and Cole(Nathanial). I was unsure on how to find the growth rate for question 2 on why the time was different from my guess of 9.9 seconds and the given time 5 seconds, so I asked chatGPT which showed me finding the ratio of the two runtimes finds the growth rate. I also asked for help from the TA in lab and office hours. I also watched this video on caches https://www.youtube.com/watch?v=bPvW4uAYj_A.

I submitted this work Fall 2024.

I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.
