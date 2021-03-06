# Approaches
  - A1: Add auxiliary information when upper bound of an array is known.
  - B1: Let we have 2 sets and xor'ing them yields x^y where x is from one and y from another set.  
    - Find XOR of S1 and S2
    - As per the property of XOR, same elements will cancel out and we will be left with 2 XOR 4 = 6 (110). But we don’t know the exact numbers,let them be X and Y.
    - A bit is set in xor only if corresponding bits in X and Y are different. This is the crucial step to understand.
    - We take a set bit in XOR. Let us consider the rightmost set bit in XOR
    - Find all the elements in S1 and S2 where that bit is set. Call it P1
    - Find all the elements in S1 and S2 where that bit is unset. Call it P2
    - Xoring all the elements in P1 will give one of x or y
    - And the other will be obtained from xoring elements of P2.


# __Array__
  - 665:Non-decreasingArray
    - Example: A = [a b c  d]
      - Find all pairs such that A[i] > A[i+1]
        - If more that one such pairs, return false
        - We have one pair
          -  Let the pair be A[i] = b  and A[i+1] = c
          -  Try modifying b
              - We have  a <= b and b > c; Also b cannot be > c
                - So for the series to be in order we must have a <= c
          - Try Modifying c
            - We have  b > c && c <= d; Also c cannot be > d
              -  So for the series to be in order we must have b <= d
    - Example: 3 4 2 3
      - Pair: 4 2
        - Try modifying 4
          - Not possible as modified value can be at max 2, but 3 is not <= 2
        - Try modifying 2
          - Not possible as modified value can be at max 3, but 4 is not <= 3
    - Example 1 4 2 3
      - 4 is modifiable is the pair 4 2
    - Example 3 4 2 4
      - 2 is modifiable is the pair 4 2

# __Math__
  - 657: JudgeRouteCircle
    - Option 1 : Use two variable to track the vertical and horizontal movements.
      At the end of the input string check if total horizontal movement == total vertical movement == 0  
    - Option 2: Use just a single variable.
  - __HashMap__
    - 645: SetMismatch
      - Option 0: Sort it and find duplicates and as we know the possible numbers we will know which one is missing
      - Option1: A map is used to find duplicates and  use the sum to find the missing number.
      - Option 2: Use a fixed size (== length of input)array.
        - In one pass find the one which is duplicate by tagging the array
        - In second, find the one which is not tagged and hence the missing one.
      - Option 3: Use Math
        - S' - x + y = S && S'^2 - x^2 + y^2 = S^2
      - Option 4: A1
      - Option 5: B1
