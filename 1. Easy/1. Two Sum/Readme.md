# Simple, beginner-friendly explanation (step-by-step)

**What the code does in one sentence:**
Given an integer array `nums` and a `target`, it finds two different indices `i` and `j` such that `nums[i] + nums[j] == target`, and returns those two indices.

---

## Big idea (intuition)

Instead of checking every pair (which is slow), the code remembers numbers it has seen so far in a `HashMap` that maps a *value → the index where that value appears*. For each number `x` it looks for `target - x` (the *complement*). If the complement is already in the map, we found the pair.

---

## Line-by-line (easy)

1. `HashMap<Integer, Integer> map = new HashMap<>();`

   * Create an empty map. Key = a number from the array, Value = that number’s index.

2. `for (int i = 0; i < nums.length; i++) {`

   * Loop over each index `i` in the array.

3. `int complement = target - nums[i];`

   * Compute the number we need to add to `nums[i]` to reach `target`.
   * Example: if `target = 9` and `nums[i] = 2`, then `complement = 9 - 2 = 7`.

4. `if (map.containsKey(complement)) { return new int[]{ map.get(complement), i }; }`

   * If the complement is already in the map, return the stored index of the complement and the current index `i`.
   * These two indices are the answer.

5. `map.put(nums[i], i);`

   * If complement wasn’t found, store the current number with its index in the map so future numbers can match with it.

6. `return new int[]{};`

   * If the loop finishes with no result, return an empty array (no pair found).

**Important detail:** we check `map.containsKey(...)` **before** inserting the current number into the map. This prevents using the same element twice (e.g., returning the same index twice).

---

## Walkthrough example (table)

Array `nums = [2, 7, 11, 15]`, `target = 9`

|  i | nums[i] | complement = target - nums[i] | Map before this iteration (value → index) | Action                                           |
| -: | ------: | ----------------------------: | ----------------------------------------: | :----------------------------------------------- |
|  0 |       2 |                     9 - 2 = 7 |                                     `{ }` | 7 not found → put `2→0`. Map now `{2→0}`         |
|  1 |       7 |                     9 - 7 = 2 |                                   `{2→0}` | 2 found → return `[ map.get(2)=0, 1 ]` → `[0,1]` |

So the function returns `[0, 1]` because `nums[0] + nums[1] == 2 + 7 == 9`.

---

## Why this is efficient

* Each element is processed once → **O(n)** time (n = `nums.length`).
* The map may store up to n entries → **O(n)** extra space.
* Much faster than a double loop (which would be **O(n²)**).

---

## Edge cases & notes

* Indices are **0-based** (first element has index 0).
* Works with duplicate values (e.g., `[3,3]`, `target=6`): store first `3→0`, on second `3` you find complement 3 and return `[0,1]`.
* If no pair exists, it returns an empty array—some problems may prefer throwing an exception or returning `null` or a fixed-size `int[2]`—adjust as needed.
* If you put the current number into the map **before** checking, you could accidentally match the number with itself and return the same index twice (wrong). That’s why `containsKey` check happens first.

---

## Quick summary (cheat-sheet)

* `map` stores numbers we’ve seen mapped to their index.
* For each `x`, compute `complement = target - x`.
* If complement exists in map → we found two indices.
* Else store `x` in the map and continue.
* Time: **O(n)**, Space: **O(n)**.

---

If you want, I can show another traced example (with duplicates or negative numbers), or rewrite the method to throw an exception when no solution exists. Which would help you learn more?
