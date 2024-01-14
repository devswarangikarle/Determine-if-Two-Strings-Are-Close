# Determine-if-Two-Strings-Are-Close

from collections import Counter

class Solution:
    def closeStrings(self, word1, word2):
        count1 = Counter(word1)
        count2 = Counter(word2)
        
        if sorted(count1.values()) == sorted(count2.values()):
            # Check if the sets of characters are the same
            set1 = set(word1)
            set2 = set(word2)
            
            return set1 == set2 or sorted(set1) == sorted(set2)
        
        return False

solution_instance = Solution()
word1 = "abc"
word2 = "bca"
print(solution_instance.closeStrings(word1, word2))  # Output: True

word1 = "a"
word2 = "aa"
print(solution_instance.closeStrings(word1, word2))  # Output: False

word1 = "cabbba"
word2 = "abbccc"
print(solution_instance.closeStrings(word1, word2))  # Output: True
