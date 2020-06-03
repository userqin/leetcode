# 804. Unique Morse Code Words \(E\)

### [Problem link](https://leetcode.com/problems/unique-morse-code-words/)

### Problem statement



International Morse Code defines a standard encoding where each letter is mapped to a series of dots and dashes, as follows: `"a"` maps to `".-"`, `"b"` maps to `"-..."`, `"c"` maps to `"-.-."`, and so on.

For convenience, the full table for the 26 letters of the English alphabet is given below:

```text
[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
```

Now, given a list of words, each word can be written as a concatenation of the Morse code of each letter. For example, "cba" can be written as "-.-..--...", \(which is the concatenation "-.-." + "-..." + ".-"\). We'll call such a concatenation, the transformation of a word.

Return the number of different transformations among all words we have.

```text
Example:
Input: words = ["gin", "zen", "gig", "msg"]
Output: 2
Explanation: 
The transformation of each word is:
"gin" -> "--...-."
"zen" -> "--...-."
"gig" -> "--...--."
"msg" -> "--...--."

There are 2 different transformations, "--...-." and "--...--.".
```

**Note:**

* The length of `words` will be at most `100`.
* Each `words[i]` will have length in range `[1, 12]`.
* `words[i]` will only consist of lowercase letters.

### Analysis

### Solution

{% tabs %}
{% tab title="Python" %}
```python
class Solution(object):
    def uniqueMorseRepresentations(self, words):
        """
        :type words: List[str]
        :rtype: int
        #2020-06-02
        """
        d = { 'a': ".-",
             'b':"-...",
             'c':"-.-.",
             'd':"-..",
             'e':".",
             'f':"..-.",
             'g':"--.",
             'h':"....",
             'i':"..",
             'j':".---",
             'k':"-.-",
             'l':".-..",
             'm':"--",
             'n':"-.",
             'o':"---",
             'p':".--.",
             'q':"--.-",
             'r':".-.",
             's':"...",
             't':"-",
             'u':"..-",
             'v':"...-",
             'w':".--",
             'x':"-..-",
             'y':"-.--",
             'z':"--.."}
        stack = []
        for word in words:
            tmp = ''
            for s in word:
                tmp += d[s]
            stack.append(tmp)
        return len(set(stack))
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def uniqueMorseRepresentations(self, words):
        """
        :type words: List[str]
        :rtype: int
        #2020-06-02
        """
        val = [".-","-...","-.-.","-..",".","..-.","--.","....",
        "..",".---","-.-",".-..","--","-.","---",".--.","--.-",
        ".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
        letters = 'abcdefghijklmnopqrstuvwxyz'
        d = {}
        for i in range(26):
            d[letters[i]] = val[i]
        stack = []
        for word in words:
            tmp = ''
            for l in word:
                tmp += d[l]
            stack.append(tmp)
        return len(set(stack))
```
{% endtab %}

{% tab title="" %}
```python

```
{% endtab %}

{% tab title="" %}
```python

```
{% endtab %}

{% tab title="" %}
```python

```
{% endtab %}
{% endtabs %}

### References

