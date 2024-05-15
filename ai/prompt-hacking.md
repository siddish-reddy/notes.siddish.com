---
description: Incremental challenges to get good at understanding LLMs
---

# 🎮 Prompt Hacking

#### Learn prompting by hacking around:

{% hint style="info" %}
Hint: Try these with smaller/old/text models which show log losses to get the intuition faster.
{% endhint %}

<details>

<summary>Tic Tac Toe                                                      (Easy, Structured Generation)</summary>

Chatgpt free version itself can play tic tac toe. But prompt the bot that wont lose but Draws or Wins if you make a mistake.

* First move will be from Human.
* Add explainability of why the bot made that move.

</details>

<details>

<summary>Is that a yes or no?                             (Few shot, Inner monologue, Classification, Medium)</summary>



Examples the prompt should work on

```python
Q: Do you have a car?
R: I bought a green Austin-Healey 3000 last week.
```

```python
Q: Are you going to pick up the blue block?
R: The blue block is sticky
```

```python
Q: Is Mark here
R: His daughter has the measles
```

```python
Q: Do you have Netflix or Prime?
R: I have Hotstar
```

```python
Q: Do you want to hear that story?
R: ️😍
```

Solution inspiration

* spoiler ahead:

<!---->

* [https://aclanthology.org/W94-0322.pdf](https://aclanthology.org/W94-0322.pdf) or a longer version by same authors: [https://aclanthology.org/J99-3004.pdf](https://aclanthology.org/J99-3004.pdf)

</details>

<details>

<summary>Solve me today’s Wordle                               (Instructional, Medium)</summary>

To keep it more challenging try to do with as many less examples as possible or using smaller models than 3.5 turbo

[Wordle - A daily word game](https://www.nytimes.com/games/wordle/index.html)

(DM for solution)

</details>

<details>

<summary>Don’t judge me (Big 5 traits)                     (Chain of Thought, Extraction, Domain)</summary>

If we give a dialogue between two persons that is sufficient enough to extract all 5 traits, write a prompt that can map the persons into their respective 3 scale likert Big 5 traits

Example:

John:

Openness: Low

Conscientiousness: High

Extraversion: Neutral

Agreeableness: Low

Neuroticism: Unsure

</details>

<details>

<summary>Your Design Thinking Intern                        (Domain, Instructional, Chaining )      </summary>

If we give couple user problem statements, like:

```python
Customer 1: The power button on my phone is broken. The warranty is still valid.
Customer 2: My display stopped working.
Customer 3: The customer service rep didn't answer my email.
Customer 4: Every time I call customer support I get no answer.
Customer 5: The display screen cracked and it's still under warranty.
Customer 6: My power button fell off the phone. That's ridiculous.
Customer 7: I'm so frustrated with this company.
Customer 8: When I use the power button too much, it stops working.
```

follow design thinking ideas loosely to come up with **a list of solutions** ranked using any product prioritisation framework.

Bonus: Do one day version, one week version and 11 star rating versionn for each problem.

![](<../.gitbook/assets/image (13).png>)

_Note: Doesn't have to generate working brilliant ideas, just learn to seperate roles and context_

Spoiler: [Rough solution inspiration](https://github.com/alexchaomander/SK-Recipes/tree/main/e6-design-chain/skills/DesignThinkingSkill)

</details>

<details>

<summary>Late night show Monologue Jokes             (Chain of Thought, Domain Knowledge, Tools)</summary>

Make AI write a joke given a news item

References:

* [Joke Writing Workshop Archives - Joe Toplyn](https://joetoplyn.com/category/joke-writing-workshop/)
* 6 characteristics every good monologue joke topic must have by Joe Toplyn

</details>

<details>

<summary>Solution Spoiler for: Late night show Monologue Jokes</summary>

![](<../.gitbook/assets/image (14).png>)

[https://arxiv.org/pdf/2306.13195.pdf](https://arxiv.org/pdf/2306.13195.pdf)



Tools:

[Pyphen - Hyphenation in pure Python](https://pyphen.org/)

Internet search: Niche pop cult![](<../.gitbook/assets/image (15).png>)ure, latest similar news

</details>

***

WIP

```
Movie Recommender                       (Planning, Embeddings, HyDE)
```

```
                                        (Sub-question decomposition) 
```

```
                                           (Theory of Mind)
```

```
                                               (Agents)
```

```
                                        (Criticism, Retrospection)
```
