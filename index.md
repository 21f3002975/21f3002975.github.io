---
layout: default
title: "Lets Count"
mathjax: true
---

# Counting with Stories

## The Story of Counting: From Pebbles to Probability

Long before equations, calculators, or even written language, humans were counting.

Imagine a shepherd, thousands of years ago, watching over his flock in the fading light of dusk. With no numerals or notations, he dropped a pebble into a pouch for every sheep that wandered past his hut at night. The next morning, he poured the pebbles out and, one by one, matched them to the sheep leaving the pen. If one pebble remained, he knew a sheep was missing. This wasn’t math as we think of it—but it was counting in its most primal form: a method to track, compare, and reason.

Over time, fingers gave way to tally marks etched on bones and stones. As trade and civilizations grew, so did the complexity of counting. The Egyptians tracked harvests, the Babylonians devised base-60 counting systems, and merchants used tokens and abacuses to track inventories and debts.

But counting wasn’t just about keeping track. It became a tool for exploring possibilities.

### The Rise of Structured Counting

In ancient India and the Islamic Golden Age, scholars began to ask deeper questions:  
*“In how many ways can you arrange objects?”*  
*“What happens if repetitions are allowed?”*  
These questions gave birth to early theories of permutations and combinations— the building blocks of what we now call combinatorics.

Centuries later, in 17th-century Europe, minds like Blaise Pascal and Pierre de Fermat formalized counting in the context of uncertainty. Their letters back and forth laid the foundation for probability theory—a revolutionary idea that chance could be measured, predicted, and even calculated.

Counting, once a shepherd’s survival skill, had become a scientific discipline.

### From Enlightenment to Algorithms

As the world entered the era of reason and then computation, counting evolved again. It became abstract—rooted in algebraic structures and functions. Mathematicians developed:

- Generating functions to encode sequences
- Partitions to explore sums of integers
- Set theory and group theory to analyze symmetry and structure

In the 20th and 21st centuries, counting took on new forms through statistical physics and computer science. Combinatorics now powers everything from quantum state calculations to AI search algorithms, from data compression to genome sequencing.

### Why Counting Still Matters

Today, counting helps us:

- Compute probabilities  
- Analyze algorithms  
- Model uncertainty  
- Optimize decisions  
- Understand patterns in nature, code, and chaos  

It’s no longer just about how many sheep are in a field—but how many ways those sheep can be arranged, selected, encoded, or predicted.

Counting is no longer just arithmetic. It’s a language—one we use to describe the possible, the probable, and the profound.

## Counting, Probabilities and Statistics

As counting matured into a mathematical discipline, it became a foundation for understanding uncertainty—giving rise to the fields of probability and statistics. Before we can assign probabilities to outcomes or reason about randomness, we must first know how to count the possible arrangements or selections that underlie those outcomes. 


We can divide the standard counting problems into four standard categories, based on two binary questions:

- **Are repetitions allowed?** (Replacement)
- **Does order matter?**

These yield **four fundamental models** of counting:


| Model | Replacement | Order Matters | Example |
|-------|-------------|----------------|---------|
| 1. Ordered with Replacement | Yes | Yes | Setting a 4-digit PIN (digits can repeat) |
| 2. Ordered without Replacement | No | Yes | Assigning top 3 race positions from 10 runners |
| 3. Unordered without Replacement | No | No | Choosing 5 cards from a deck (e.g., poker hand) |
| 4. Unordered with Replacement | Yes | No | Selecting 3 scoops of ice cream (order irrelevant) from 5 flavors |

---

## The Big Four: Table of Counting Models

We can divide counting problems into four standard categories, based on two binary questions:
- **Are repetitions allowed?** (Replacement)
- **Does order matter?**

These yield **four fundamental models** of counting:

|                       | Order Matters               | Order Doesn't Matter   |
|-----------------------|-----------------------------|------------------------|
| **With Replacement**  | $$ n^k $$                   | $$ \binom{n + k - 1}{k} $$ |
| **Without Replacement** | $$ \frac{n!}{(n - k)!} $$ | $$ \binom{n}{k} $$ |

Where:
- \( n \) = total number of distinct items
- \( k \) = number of selections

---

## Detailed Analysis of Each Model

### 1. **Ordered with Replacement**
#### i. Algebraic Proof
We are choosing \( k \) items from \( n \), and every item can be chosen again.
Each of the \( k \) positions has \( n \) choices.
$$ n \times n \times \cdots \times n = n^k $$


#### ii. Story Proof
Imagine setting a 4-digit password. Each digit (slot) has 10 options (0-9), regardless of earlier choices. Total = \( 10^4 = 10,000 \).

<br><br>

<iframe src="/visualizations/ordered-replacement.html" width="100%" height="450" style="border: 1px solid #ccc; border-radius: 8px;"></iframe>

<br><br>

#### iii. Double Counting
Count the total number of functions from a set \( \{1,2,...,k\} \) (positions) to \( \{1,2,...,n\} \) (items). There are $$ n^k $$ such functions.

---
### 2. **Ordered without Replacement**
#### i. Algebraic Proof
First slot has \( n \) options, next has \( n - 1 \), and so on:
$$ P(n, k) = \frac{n!}{(n - k)!} $$

#### ii. Story Proof
Choosing top 3 winners in a race with 10 runners. You cannot assign the same runner to more than one position.
First place: 10 options, Second: 9, Third: 8. Total = $$ 10 \times 9 \times 8 $$

<iframe src="/visualizations/ordered-no-replacement.html" width="100%" height="450" style="border: 1px solid #ccc; border-radius: 8px;"></iframe>


#### iii. Double Counting
Count the number of injective functions from a set \( \{1,2,...,k\} \) to \( \{1,2,...,n\} \):
$$ P(n, k) $$ is the count of such injective mappings.

---

### 3. **Unordered with Replacement**
#### i. Algebraic Derivation

We are selecting \( k \) items from \( n \), with repetition and no order. This is equivalent to placing \( k \) indistinguishable balls into \( n \) distinguishable boxes.
- Using "stars and bars":
$$ \binom{n + k - 1}{k} $$

#### ii. Story Proof
Choose 3 scoops of ice cream (from 5 flavors), flavors can repeat, order doesn’t matter. E.g., (Vanilla, Vanilla, Chocolate).
This becomes a question of how many ways to assign 3 indistinct scoops to 5 flavor types.

<iframe src="/visualizations/unordered-replacement.html" width="100%" height="450" style="border: 1px solid #ccc; border-radius: 8px;"></iframe>

#### iii. Double Counting
Translate to placing \( k \) stars (choices) and \( n - 1 \) bars (dividers between types).
Total sequences = $$ \binom{n + k - 1}{k} $$.

---


### 4. **Unordered without Replacement**
#### i. Algebraic Proof
We want to select \( k \) distinct items, order doesn’t matter:
$$ \binom{n}{k} = \frac{n!}{k!(n-k)!} $$

#### ii. Story Proof
Forming a committee of 3 people from a group of 10. The group members have no roles or ranks.

<iframe src="/visualizations/unordered-no-replacement.html" width="100%" height="450" style="border: 1px solid #ccc; border-radius: 8px;"></iframe>

#### iii. Double Counting
Count permutations first: $$\frac{n!}{(n-k)!} $$, then divide by $$ k! $$ to account for ordering: $$ \text{Permutations} \div \text{orderings} = \frac{n!}{k!(n-k)!} $$

---

## Parting Thoughts

Understanding these models is essential in:

- Solving real-world problems in probability.
- Interpreting probabilistic models in AI, statistics, and physics.
- Building foundational intuition for deeper topics (Bayes, distributions, expectation).



