---
layout: default
title: "Lets Count"
mathjax: true
---

# Counting with Stories

## The Story of Counting: From Pebbles to Probability

Long before equations, calculators, or even written language, humans were counting.
<br><br>
Imagine a shepherd, thousands of years ago, watching over his flock in the fading light of dusk. With no numerals or notations, he dropped a pebble into a pouch for every sheep that wandered past his hut at night. The next morning, he poured the pebbles out and, one by one, matched them to the sheep leaving the pen. If one pebble remained, he knew a sheep was missing. This wasn’t math as we think of it—but it was counting in its most primal form: a method to track, compare, and reason.
<br><br>
Over time, fingers gave way to tally marks etched on bones and stones. As trade and civilizations grew, so did the complexity of counting. The Egyptians tracked harvests, the Babylonians devised base-60 counting systems, and merchants used tokens and abacuses to track inventories and debts.
<br><br>
But counting wasn’t just about keeping track. It became a tool for exploring possibilities.

### The Rise of Structured Counting

At the turn of the first millennium, scholars began to ask deeper questions:  
*“In how many ways can you arrange objects?”*  
*“What happens if repetitions are allowed?”*  
These questions gave birth to early theories of permutations and combinations— the building blocks of what we now call combinatorics.
<br><br>
Centuries later, in 1700s Europe, minds like Blaise Pascal and Pierre de Fermat formalized counting in the context of uncertainty. Their letters back and forth laid the foundation for probability theory—a revolutionary idea that chance could be measured, predicted, and even calculated.
<br><br>
Counting, once a shepherd’s survival skill, had become a scientific discipline.

### From Enlightenment to Algorithms

As the world entered the era of reason and then computation, counting evolved again. It became abstract—rooted in algebraic structures and functions. Mathematicians developed:
<ul style="margin-left: 2em;">
  <li>Generating functions to encode sequences</li>
  <li>Partitions to explore sums of integers</li>
  <li>Set theory and group theory to analyze symmetry and structure</li>
</ul>

<br><br>
In the 20th and 21st centuries, counting took on new forms through statistical physics and computer science. Combinatorics now powers everything from quantum state calculations to AI search algorithms, from data compression to genome sequencing.

---

## Counting, Probabilities and Uncertainity

As counting matured into a mathematical discipline, it became a foundation for understanding uncertainty—giving rise to the fields of probability and statistics. Before we can assign probabilities to outcomes or reason about randomness, we must first know how to count the possible arrangements or selections that underlie those outcomes. 
<br><br>
In **probability**, counting provides a way to calculate the likelihood of events. Probabilities are defined as ratios:

$$
P(A) = \frac{\text{Number of favorable outcomes}}{\text{Number of possible outcomes}}
$$

This simple formula relies entirely on accurate counting. Whether you're computing the odds of drawing a full house in poker or determining the chance of flipping 3 heads in 5 coin tosses, counting is indispensable. As problems get more complex, so does the need for structured counting models.

### Order and Replacement

Before we begin counting, we must ask ourselves the question: What exactly are we counting? More specifically, we are concerned with
<br><br>
**Order** - Are we counting simply the number of combinations of outcomes or their arrangements as well? 
Consider **flipping two coins**, is there a difference between the outcomes **(tails, heads) and (heads, tails)**? If order matters then they are not the same.
<br><br>
**Replacement** – Does choosing an item remove it from future selections, or is it still available? Does it affect the possible outcomes of subsequent events? 
<br><br>
Imagine you're selecting a **book to read from a digital library app** that has 3 featured books on the homepage. Each time you open the app, you're allowed to choose one of the books to read for a while and then return it. Since the books are digital and nothing is physically removed from the collection, you can choose the same book again later. This is a situation with **replacement**—each selection doesn't change the set of available options for the next round.
<br><br>
Compare that to a physical book fair, where if you pick a book and take it home, it's no longer on the shelf. The remaining options shrink after each selection—that's **without replacement**.
<br><br>
Answering these two questions on order and repitition yields 4 separate categories of counting problems,


| Model | Replacement | Order Matters | Example |
|-------|-------------|----------------|---------|
| 1. Ordered with Replacement | Yes | Yes | Setting a 4-digit PIN (digits can repeat) |
| 2. Ordered without Replacement | No | Yes | Assigning top 3 race positions from 10 runners |
| 3. Unordered without Replacement | No | No | Choosing 5 cards from a deck (e.g., poker hand) |
| 4. Unordered with Replacement | Yes | No | Selecting 3 scoops of ice cream (order irrelevant) from 5 flavors |


Prior to getting into each coutjing problem and its solutions, let us take a quick detour and learn a powerful tool to solve coutning problems in general. This is particularly useful in combinatorics. It is called the **Story Proof** !

## The Power of Story Proofs in Counting

When faced with a complex-looking combinatorial identity, it’s tempting to dive straight into algebra: expanding factorials, simplifying expressions, and trying to manipulate your way to a solution. But in combinatorics, there's a different, often more intuitive technique—**story proofs**, also known as **combinatorial arguments**.

### What is a Story Proof?

A story proof doesn’t rely on manipulating symbols. Instead, it relies on **understanding what the expression actually counts**, and then telling a different “story” that counts the same thing in another way.
<br><br>
At its heart, a story proof answers the question:
<br><br>
> *Can I interpret both sides of this identity as counting the same thing, but from different perspectives?*
<br><br>
This approach not only simplifies many problems, but often reveals *why* an identity is true—something that pure algebra may obscure.


### Vandermonde's Identity via Story Proof

### The Identity

$$
\sum_{j=0}^k \binom{m}{j} \binom{n}{k - j} = \binom{m + n}{k}
$$

At first glance, this looks intimidating—an unfamiliar summation of products of binomial coefficients. But with a good story, it becomes beautifully clear.

### The Story

Suppose you have two groups:
<br><br>
**Group A** has **m** people
**Group B** has **n** people

Together, there are **m + n** people. Now, you want to form a **committee of k people** from this combined group. That’s what the **right-hand side** is doing:

$$
\binom{m + n}{k}
$$

It counts the number of ways to choose k people from the total m + n.
<br><br>
But now, let’s count the same thing a different way.

### The Left-Hand Side

Let’s decide **how many people to pick from Group A** and how many from Group B. Suppose we pick **j people from Group A**. Then, we must pick **k - j people from Group B** to reach k total.

&nbsp;&nbsp;&nbsp;&nbsp;• Number of ways to choose j people from Group A: $\binom{m}{j}$
&nbsp;&nbsp;&nbsp;&nbsp;• Number of ways to choose k - j people from Group B: $\binom{n}{k - j}$

Now sum over all possible values of j (from 0 to k), and you’ve accounted for **every way to form a k-person committee from two groups**, by considering all possible combinations of contributions from Group A and B.
<br><br>
That’s exactly what the **left-hand side** is doing:

$$
\sum_{j=0}^k \binom{m}{j} \binom{n}{k - j}
$$

### Why This Matters

Algebraically, proving this identity is messy—it requires manipulating binomial coefficients and careful bookkeeping. But the story proof is:

&nbsp;&nbsp;&nbsp;&nbsp;• Clean  
&nbsp;&nbsp;&nbsp;&nbsp;• Visual  
&nbsp;&nbsp;&nbsp;&nbsp;• Intuitive

And most importantly, it shows *why* the identity is true—not just *that* it is.
<br><br>
Story proofs like this are a central technique in combinatorics because they link **counting** to **context**. They turn numbers into narratives—and in doing so, reveal patterns that algebra alone might hide.

---

Now let us get back to the main focus of our article.

## The Big Four

Thus far, we have seen that answering these two questions, helps us categorize the counting problems into 4 sub-categories.
- **Does order matter?**
- **Are repetitions allowed?** (Replacement)

And the solutions to these **four counting problems**are as follows:

|                       | Order Matters               | Order Doesn't Matter   |
|-----------------------|-----------------------------|------------------------|
| **With Replacement**  | $$ n^k $$                   | $$ \binom{n + k - 1}{k} $$ |
| **Without Replacement** | $$ \frac{n!}{(n - k)!} $$ | $$ \binom{n}{k} $$ |

Where:
- \( n \) = total number of distinct items
- \( k \) = number of selections

---

## Details of each Counting method

We building the algebric solutions for each counting problem, we will use story proofs where required.

Imagine, you have downloaded a new app and it requires that you set a 4 digit PIN. In how many ways can you do it. For simplicity, let us restrict the options to these 10 digits : $0,1,2, \ldots,8, 9$. 

But before starting to solve it, spend a minute thinking of those two questions - **1) Does order matter? 2) Are repititions allowed?** The answer to the first one is yes order matters. In case of the latter, it usually depends on the application. In some case they may restrict repitition. In our case let us assume that repitition is allowed. And this takes us to our first category of counting problems.

### 1. **Ordered with Replacement**

**The standard way of phrasing this set of counting problems is : in how many ways can I choose $k$ items from $n$ choices, when order matters and replacement is allowed?**

#### Solution : $ n^k $

Going back to our password example. We have 4 positions to fill from 10 choices ($0,1,2, \ldots,8, 9$) and we can look at the choice for each position as an individual event with 10 different outcomes(corresponding to the 10 digits). 
- For position 1, we can thus count 10 possible outcomes.
- What about for position 2? As our choice for position 1 is not consumed, we can choose the same digit again – or we can choose a different digit. We still have 10 possible outcomes – and we count these 10 outcomes for each different outcome from position 1.

We can now write the overall $10 * 10$ ways of making a choice. Continuting this we get $10^4 = 10,000$ choices for the 4 digit PIN. 

Now generalize this argument for k positions with n choices for each position. We are choosing \( k \) items from \( n \), and every item can be chosen again.
- Each of the \( k \) positions has \( n \) choices.
- $$ n \times n \times \cdots \times n = n^k $$

Below is a simulation for illustration, go ahead tinker with it.

<br>

<iframe src="/visualizations/ordered-replacement.html" width="100%" height="450" style="border: 1px solid #ccc; border-radius: 8px;"></iframe>

<br>

#### ii. Story Proof
Imagine setting a 4-digit password. Each digit (slot) has 10 options (0-9), regardless of earlier choices. Total = \( 10^4 = 10,000 \).



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



