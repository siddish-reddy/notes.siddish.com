---
description: Tricks and Techniques for Engineer friends
---

# ℹ Prompting

> “A large part of the difference between the experienced decision maker and the novice in these situations is not any particular intangible like judgment or intuition. If one could open the lid, so to speak, and see what was in the head of the experienced decision-maker, one would find that he had at his disposal repertoires of possible actions, that he had checklists of things to think about before he acted; and that he had mechanisms in his mind to evoke these, and bring these to his conscious attention when the situations for decisions arose.” - Farnam Street



### **Prompt Workflow:**



**1.  Do 3 scenarios manually**

Be aware exactly what is going on in your mind, are you maintaining a checklist of things, what are you searching for in the internet, what all are you trying to recall, do you have the urge to write a python script to do this instead? etc



**2.  Map manual process to AI metaphors:**

Inner Monologue, Internet Search, Knowledge Base, Code Generation, Image Search.



**3.  Train the needed skill to AI:**

Consider your 6th standard cousin (basic logical, cognitive, creative skills, some coding and writing, small attention span) and estimate how much time would it take for them to learn the required skills.

Roughly, if you think you can teach them in 10 minutes, start with zero shot; if it takes couple practise exercises, few shot; If it takes one hour class, GPT-4, if it takes multiple days then fine tuning.



**4.  Provide the needed knowledge to AI**

If the needed knowledge is under couple paragraphs, then in the prompt itself. If its more than couple pages, then Knowledge Base (RAG). Is that similar to open book exam, but still you first need to learn, then fine tuning + RAG.



**5.  Create test scenarios**

Couple for each rule, couple out of training examples and domains to check its generalisability, couple that violate input format and quality expectations. Ofc couple must work, ideal inputs.



**6.  Iterate**

Try different models, go from single prompt to multiple, rephrase jobs of each prompt to popular versions, play with different personas for each prompt.



### Thinking in Embeddings:

TODO



***

**Examples in Few Shot:**

Diverse\
Easy to Hard Order\
Cover all strict rules\
(if you can, give as many less examples as possible, ideal is zero)

**Format in Generation:**

Skeleton or Schema in System Instruction\
Not necessary to provide example unless the schema is not popular.

**Text Rephrase:**

Aspects to rephrase\
What not to ignore\
What to feel free with

**Chain of Thought**

Do not jump to conclusion and loosely some rationality thinking process/framework like OODA (Observe, Decide, Act). If latency is constraint, then CoT can also be like pseudo code with just keywords.



Other references to dig into:

* [System Instruction Skeleton](https://mitenmit.github.io/gpt/)
