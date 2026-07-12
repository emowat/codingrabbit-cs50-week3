## Problem to Solve

Recall from lecture that we saw a few algorithms for sorting a sequence of numbers: selection sort, bubble sort, and merge sort.

*   **Selection sort** iterates through the unsorted portions of a list, selecting the smallest element each time and moving it to its correct location. It always takes $O(n^2)$ time.
*   **Bubble sort** compares pairs of adjacent values one at a time and swaps them if they are in the incorrect order. This continues until the list is sorted. It takes $O(n^2)$ time, but can be optimized to stop early if the list is already sorted (taking $\Omega(n)$ time).
*   **Merge sort** recursively divides the list into two repeatedly and then merges the smaller lists back into a larger one in the correct order. It always takes $O(n \log n)$ time.

In this assignment, you will download three already-compiled sorting programs: `sort1`, `sort2`, and `sort3`. Each implements a different sorting algorithm (selection, bubble, or merge sort), but you don't know which is which! 

Your task is to analyze these programs by timing how long they take to sort various input files, and determine which algorithm each program is using.

*For full details on this problem, read the official instructions here: [CS50 Sort Instructions](https://cs50.harvard.edu/x/psets/3/sort/)*

## How to Begin

You need to download the "distribution code" which contains the compiled programs and the text files. 

Open the terminal window at the bottom of your screen. Ensure your terminal is in the main workspace directory (it should look like `student@codespace:/workspaces/codingrabbit-cs50-week3$`). 

Run the following commands one by one to download the ZIP file, extract it, and clean up the ZIP:

```bash
curl -O https://cdn.cs50.net/2026/x/psets/3/sort.zip
unzip sort.zip
rm sort.zip
```

Extracting the ZIP will automatically populate this `sort` folder with the compiled binaries and data files! Now, change your terminal directory into this folder:

```bash
cd sort
```

You can now use the `code` command to open the answers file in the editor:

```bash
code answers.txt
```

## Instructions

1.  **Understand the Inputs:** You now have three types of text files:
    *   **Sorted** (e.g., `sorted10000.txt`): The numbers are already in order.
    *   **Reversed** (e.g., `reversed10000.txt`): The numbers are backwards.
    *   **Random** (e.g., `random10000.txt`): The numbers are completely shuffled.
2.  **Time the Sorts:** Use the `time` command in your terminal to see how long a sort takes. For example, to time how long `sort1` takes to sort 10,000 reversed numbers, run:
    ```bash
    time ./sort1 reversed10000.txt
    ```
    Look at the `real` time output to see how many seconds elapsed.
3.  **Analyze the Results:** Test `sort1`, `sort2`, and `sort3` on the different files. 
    *   Does one of them finish instantly on the `sorted` files? (That might be bubble sort!).
    *   Is one of them consistently fast across all files, even the random 50,000 file? (That might be merge sort!).
    *   Is one of them consistently slow regardless of whether the file is sorted or reversed? (That might be selection sort!).
4.  **Record Your Answers:** Fill in the blanks marked `TODO` in `answers.txt` with the name of the sort and a brief explanation of how you deduced it.

## How to Test

If you get stuck trying to identify the algorithms, remember to **click the Coding Rabbit icon** on the left sidebar to ask your AI Teaching Assistant for hints!
