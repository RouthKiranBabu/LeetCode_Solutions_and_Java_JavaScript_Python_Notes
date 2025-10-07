Nice — this is a classic, neat trick to check if an integer is a palindrome **without converting it to a string**. I’ll explain it step-by-step and walk through examples so it’s easy to follow.

# Quick idea (one sentence)

Reverse only **half** of the digits and then compare that reversed half with the remaining half. This avoids reversing the whole number and avoids overflow.

# Annotated code (short)

```java
class Solution {
    public boolean isPalindrome(int x) {
        // Negative numbers and numbers ending with 0 (but not 0 itself) are not palindrome
        if (x < 0 || (x % 10 == 0 && x != 0)) return false;

        int reversedHalf = 0;
        while (x > reversedHalf) {
            reversedHalf = reversedHalf * 10 + x % 10;
            x /= 10;
        }

        // If number has odd digits, ignore the middle digit (reversedHalf / 10)
        return x == reversedHalf || x == reversedHalf / 10;
    }
}
```

# Line-by-line in plain English

1. `if (x < 0 || (x % 10 == 0 && x != 0)) return false;`

   * Negative numbers are not palindromes (because of the minus sign).
   * Any number that ends with `0` but is not `0` itself cannot be palindrome (e.g., `10` vs `01`).

2. `int reversedHalf = 0;`

   * We'll build the reversed value of the last half of the digits here.

3. `while (x > reversedHalf) { ... }`

   * Keep taking digits from the end of `x` and appending them to `reversedHalf` until we've processed *at least half* the digits.
   * Stopping condition `x > reversedHalf` ensures we stop when we've reversed half (for even digit counts) or just past half (for odd digit counts).

4. Inside loop:

   * `reversedHalf = reversedHalf * 10 + x % 10;` → take last digit of `x` and append it to `reversedHalf`.
   * `x /= 10;` → drop that last digit from `x`.

5. `return x == reversedHalf || x == reversedHalf / 10;`

   * If digits are even: after loop both halves should be equal → `x == reversedHalf`.
   * If digits are odd: `reversedHalf` includes the middle digit, so remove it by `reversedHalf/10` and compare → `x == reversedHalf/10`.

# Walkthrough examples (tables)

### Example A — even digits: `x = 1221`

|                     Iteration | before loop (x, reversedHalf) | operation         | after (x, reversedHalf) | note                                                    |
| ----------------------------: | ----------------------------: | ----------------- | ----------------------: | ------------------------------------------------------- |
|                         start |                     (1221, 0) | —                 |               (1221, 0) |                                                         |
|                             1 |                     (1221, 0) | take last digit 1 |                (122, 1) | reversedHalf = 1                                        |
|                             2 |                      (122, 1) | take last digit 2 |                (12, 12) | reversedHalf = 12                                       |
| loop stops (12 > 12 is false) |                               |                   |                         | now compare `x == reversedHalf` → `12 == 12` → **true** |

### Example B — odd digits: `x = 12321`

| Iteration |   before (x, reversedHalf) |                                                                    after (x, reversedHalf) | note                                        |
| --------: | -------------------------: | -----------------------------------------------------------------------------------------: | ------------------------------------------- |
|     start |                 (12321, 0) |                                                                                 (12321, 0) |                                             |
|         1 |                 (12321, 0) |                                                                                  (1232, 1) | took 1                                      |
|         2 |                  (1232, 1) |                                                                                  (123, 12) | took 2                                      |
|         3 |                  (123, 12) |                                                                                  (12, 123) | took 3 — now reversedHalf > x so loop stops |
|   Compare | x = 12, reversedHalf = 123 | check `x == reversedHalf` (12==123? no) or `x == reversedHalf/10` (12==12? yes) → **true** |                                             |

### Edge cases

* `x = -121` → negative → **false**.
* `x = 10` → ends with 0 but not 0 itself → **false**.
* `x = 0` → allowed → **true**.

# Why this is good

* Works without converting number → saves memory.
* Only reverses *half* the digits → faster and avoids full-number overflow.
* Clean comparisons handle both even and odd digit counts.

# Complexity

* Time: O(d) where `d` = number of digits, but effectively O(d/2) → commonly written as **O(log₁₀(x))**.
* Space: **O(1)** (constant extra space).

# Short TL;DR

Take digits from the end, build a reversed half, stop when you've reached half the digits, then compare the two halves (for odd-length numbers ignore the middle digit). If they match, the number is a palindrome.

If you want, I can show the exact variable values step-by-step for any number you choose — pick one and I’ll make a table like above.
