## string comparison
- Compare the first character of both strings.
- If the first character from the first string is greater (or less) – **in Unicode order** – than the other string’s, then the first string is greater (or less) than the second. We’re done.
- Otherwise, if both strings’ first characters are the same, compare the second characters the same way.
- Repeat until the end of either string.
- If both strings end at the same length, then they are equal. Otherwise, the longer string is greater.