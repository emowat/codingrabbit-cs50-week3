## Problem to Solve

You already know about plurality elections and instant-runoff elections. But there's another ranked-choice voting method called the **Tideman voting method** (also known as "ranked pairs"). 

The Tideman method is guaranteed to produce the "Condorcet winner" of an election if one exists. A Condorcet winner is the candidate who would win any head-to-head matchup against every other candidate. 

The Tideman method works by constructing a "graph" of candidates. An arrow from candidate A to candidate B indicates that candidate A wins against candidate B in a head-to-head matchup. The algorithm locks in the strongest victories first, as long as adding the edge doesn't create a cycle (like Rock-Paper-Scissors, where nobody wins). Once the graph is complete, the "source" of the graph (the candidate with no arrows pointing towards them) is declared the winner!

In a file called `tideman.c` in a folder called `tideman`, create a program to simulate an election by the Tideman voting method. **Note that Tideman is an optional but challenging alternative to Runoff!**

*For the full background on Condorcet winners and a detailed walkthrough of the Tideman algorithm, read the official instructions here: [CS50 Tideman Instructions](https://cs50.harvard.edu/x/psets/3/tideman/)*

## How to Begin

You need to download the "distribution code" which contains the scaffolding for the `tideman` program. 

Open the terminal window at the bottom of your screen. Ensure your terminal is in the main workspace directory (it should look like `student@codespace:/workspaces/codingrabbit-cs50-week3$`). 

Run the following commands one by one to download the ZIP file, extract it, and clean up the ZIP:

```bash
curl -O https://cdn.cs50.net/2026/x/psets/3/tideman.zip
unzip tideman.zip
rm tideman.zip
```

Extracting the ZIP will automatically populate this `tideman` folder with the `tideman.c` starter code. Now, change your terminal directory into this folder:

```bash
cd tideman
```

You can now use the `code` command to open the file in the editor:

```bash
code tideman.c
```

## Instructions

The distribution code provides the `main` function and several global data structures (like the `preferences` array, the `locked` boolean adjacency matrix, and the `pairs` array). Your job is to complete the following six functions:

1.  **`vote`**: Record the voter's rank preference for a valid candidate.
2.  **`record_preferences`**: Update the global `preferences` array based on a single voter's `ranks`.
3.  **`add_pairs`**: Add all head-to-head matchups where one candidate is preferred to the `pairs` array (ignoring ties).
4.  **`sort_pairs`**: Sort the `pairs` array in decreasing order of the "strength of victory".
5.  **`lock_pairs`**: Create the `locked` graph by adding edges in decreasing order of victory strength, *so long as the edge would not create a cycle*. (This requires recursion or path-finding!).
6.  **`print_winner`**: Print out the name of the candidate who is the source of the graph.

## How to Test

Recall that you can compile your program by running:

```bash
make tideman
```

If it compiles successfully, run your program with the names of the candidates:

```bash
./tideman Alice Bob Charlie
```

If you see an error message or get stuck trying to implement the logic (especially the cycle detection!), remember to **click the Coding Rabbit icon** on the left sidebar to ask your AI Teaching Assistant for hints!
