## Problem to Solve

You already know about plurality elections, where every voter gets one vote, and the candidate with the most votes wins. But what happens when the vote is split among three or more candidates? Sometimes, the candidate who wins the plurality of the vote isn't actually preferred by the majority of voters!

One solution is **ranked-choice voting**, such as the **Instant Runoff** system. In an instant runoff election, voters rank all candidates in order of preference. 
*   If a candidate has more than 50% of the first-preference votes, they win immediately.
*   If no candidate has a majority, the candidate with the fewest votes is eliminated.
*   Anyone who originally voted for the eliminated candidate now has their second preference counted instead. 
*   This process repeats until a candidate has a majority.

In a file called `runoff.c` in a folder called `runoff`, create a program to simulate a runoff election!

*For the full background on instant runoff voting and a detailed walkthrough, read the official instructions here: [CS50 Runoff Instructions](https://cs50.harvard.edu/x/psets/3/runoff/)*

## How to Begin

You need to download the "distribution code" which contains the scaffolding for the `runoff` program. 

Open the terminal window at the bottom of your screen. Ensure your terminal is in the main workspace directory (it should look like `student@codespace:/workspaces/codingrabbit-cs50-week3$`). 

Run the following commands one by one to download the ZIP file, extract it, and clean up the ZIP:

```bash
curl -O https://cdn.cs50.net/2026/x/psets/3/runoff.zip
unzip runoff.zip
rm runoff.zip
```

Extracting the ZIP will automatically populate this `runoff` folder with the `runoff.c` starter code. Now, change your terminal directory into this folder:

```bash
cd runoff
```

You can now use the `code` command to open the file in the editor:

```bash
code runoff.c
```

## Instructions

The distribution code provides the `main` function and several global variables/structs (like `preferences` and `candidates`). Your job is to complete the following six functions:

1.  **`vote`**: Given a voter, their rank, and a candidate's name, record the preference if it's a valid candidate.
2.  **`tabulate`**: Update the number of votes each candidate has at the current stage in the runoff (only counting top-preferred candidates who haven't been eliminated).
3.  **`print_winner`**: If any candidate has strictly more than half the vote, print their name and return true.
4.  **`find_min`**: Return the minimum number of votes any still-in-the-running candidate has.
5.  **`is_tie`**: Return true if every candidate still in the election has the same number of votes.
6.  **`eliminate`**: Eliminate the candidate (or candidates) who have the minimum number of votes.

## How to Test

Recall that you can compile your program by running:

```bash
make runoff
```

If it compiles successfully, run your program with the names of the candidates:

```bash
./runoff Alice Bob Charlie
```

If you see an error message or get stuck trying to implement the logic, remember to **click the Coding Rabbit icon** on the left sidebar to ask your AI Teaching Assistant for hints!
