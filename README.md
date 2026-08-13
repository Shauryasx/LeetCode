# LeetCode
Explaination of Two Sum Problem using ChatGPT like a 5 year old kid!!!


START:-

Absolutely! 😄 Let's understand **LeetCode Problem #1 — Two Sum** like you're **5 years old**.

## 🧸 The Problem: Two Sum

Imagine I give you some numbers:

```text
numbers = [2, 7, 11, 15]
```

And I say:

> "Find TWO numbers that add up to `9`."

You look at the numbers:

* `2 + 7 = 9` 🎉

So the answer is:

```text
[0, 1]
```

Why `0, 1`?

Because computers start counting from **0**:

```text
Index:    0   1   2   3
          ↓   ↓   ↓   ↓
Numbers: [2,  7, 11, 15]
```

The numbers we want are **2 and 7**, which are at positions **0 and 1**.

---

## 🧠 What does LeetCode actually ask?

You are given:

```text
nums = [2, 7, 11, 15]
target = 9
```

You need to find:

> Which **two numbers** add together to make the target?

So:

```text
2 + 7 = 9
```

Return:

```text
[0, 1]
```

---

# 🐌 Super Easy Method

Let's pretend you're a little kid with four candies:

```text
2  7  11  15
```

You pick the first number:

```text
2
```

Then ask:

> "What number do I need to make 9?"

We calculate:

```text
9 - 2 = 7
```

Aha! 😲

We need **7**.

And 7 is in the array!

So we return:

```text
[0, 1]
```

---

# 💻 Working Python Code

```python
class Solution:
    def twoSum(self, nums, target):
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
```

### Let's understand it VERY slowly 🐢

This:

```python
for i in range(len(nums)):
```

means:

> "Go through every number."

Then:

```python
for j in range(i + 1, len(nums)):
```

means:

> "For each number, check the numbers after it."

Then:

```python
if nums[i] + nums[j] == target:
```

means:

> "Do these two numbers add up to my target?"

If YES:

```python
return [i, j]
```

means:

> "YAY! 🎉 Give me their positions!"

---

# 🧪 Let's see it working

Suppose:

```python
nums = [2, 7, 11, 15]
target = 9
```

The computer checks:

```text
2 + 7  = 9 ✅
```

So it returns:

```text
[0, 1]
```

---

# ⚡ But there is a MUCH BETTER way

The above solution works, but it's like searching for your toy by checking **every single box**. 😭

We can use a **dictionary** (`dict`) to make it much faster.

Think of a dictionary like a little notebook 📒:

```text
number → where I found it
```

## 🚀 Better LeetCode Solution

```python
class Solution:
    def twoSum(self, nums, target):
        seen = {}

        for i, num in enumerate(nums):
            needed = target - num

            if needed in seen:
                return [seen[needed], i]

            seen[num] = i
```

Let's make this **5-year-old simple**.

Suppose:

```text
nums = [2, 7, 11, 15]
target = 9
```

### 👶 Step 1

We see:

```text
2
```

We ask:

```text
9 - 2 = 7
```

We need **7**.

Have we seen 7 before?

```text
NO ❌
```

So we remember:

```text
2 → position 0
```

---

### 👶 Step 2

Now we see:

```text
7
```

We ask:

```text
9 - 7 = 2
```

Do we already have 2 in our notebook?

```text
YES! 🎉
```

Our notebook says:

```text
2 → position 0
```

And 7 is at:

```text
position 1
```

Therefore:

```text
[0, 1]
```

🎉 Done!

---

# 🧠 The MOST IMPORTANT IDEA

Whenever you see a number:

### Ask:

> **"What number do I need to reach the target?"**

The formula is:

```text
needed = target - current_number
```

For example:

```text
target = 10
current = 3

needed = 10 - 3
needed = 7
```

So we're looking for **7**.

---

## 📝 Remember this for LeetCode

The Two Sum pattern is:

```text
1. Look at a number
2. Calculate what number you need
3. Check if you have already seen it
4. If yes → return the two indexes
5. If no → remember the current number
```

And the best solution is:

```python
class Solution:
    def twoSum(self, nums, target):
        seen = {}

        for i, num in enumerate(nums):
            needed = target - num

            if needed in seen:
                return [seen[needed], i]

            seen[num] = i
```

### ⭐ One line to memorize:

**"I don't look for two numbers. I look for the missing number."**

That's the main trick behind **Two Sum**. 🚀

END:-
