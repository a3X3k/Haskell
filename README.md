# Haskell

### Find 2nd Last Element of a list

```
secondLast :: ( Ord a ) => [ a ] -> a

secondLast list = list !! ( length list - 2 ) 
```

### Find the kth element of list, where k is the index

```py
kthElement :: ( Ord a ) => [ a ] -> Int -> a

kthElement list i = list !! i
```

### Palindrome or Not

```py
isPalindrome :: ( Ord a ) => [ a ] -> Bool

isPalindrome list = list == reverse list
```

### Remove duplicates from a given list

```py
removeDup :: ( Ord a ) => [ a ] -> [ a ]

removeDup [] = []
removeDup ( x : xs ) = x : removeDup ( remove x xs )

 where

  remove :: ( Ord a ) => a -> [ a ] -> [ a ]
  
  remove x [] = []
  remove x ( y : ys )
   | x == y = remove x ys
   | otherwise = y : ( remove x ys )
```

### Find N Prime

```py
isPrime :: Int -> Bool
isPrime n = null [i | i <- [2..floor (sqrt (fromIntegral n))], n `mod` i == 0]

nPrime :: Int -> [Int]
nPrime n = take n [x | x <- [2 .. ], isPrime x]
```

