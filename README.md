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

### Duplicate each element of the list and produce a new list

```py
adddup :: ( Ord a ) => [ a ] -> [ a ]

adddup [] = []

adddup ( x : xs ) = x : x : adddup ( xs )
```

### Replicate the elements of a list N times

```py
replic :: ( Ord a ) => [ a ] -> Int -> [ a ]

replic [] _ = []

replic ( x : xs ) n = replicate n x ++ replic xs n
```

### Remove every Nth element from the list

```py
removeNth :: [a] -> Int -> [a]

removeNth [] _ = []

removeNth xs n = take (n-1) xs ++ removeNth (drop n xs) n
```

### Divide the list into two the first n elements as the first list and the rest as the second list and form a list of lists.  

```py
splitn :: Int -> [a] -> ([a], [a])

splitn n x = (take n x, drop n x)
```

### Slice a list based on the input indices i and k. 

```py
slice :: [a] -> Int -> Int -> [a]

slice x i k = drop i (take (k+1) x)
```

### Remove the Kth indexed element from a list

```py
remk :: [a] -> Int -> [a]

remk [] _ = []

remk (x:xs) 0 = xs

remk (x:xs) n = x : remk (xs) (n-1) 
```

### Insert an element N at a particular index i of a list

```py
insertn :: [a] -> a -> Int -> [a]

insertn [] _ _ = []

insertn x element 0 = element : x

insertn (x : xs) element n = x : insertn xs element (n - 1)
```

### Find First N Primes

```py
isPrime :: Int -> Bool

isPrime n = null [i | i <- [2..floor (sqrt (fromIntegral n))], n `mod` i == 0]

nPrime :: Int -> [Int]

nPrime n = take n [x | x <- [2 .. ], isPrime x]
```

```py
nPrime :: Int -> [Int]

nPrime n = findPrime n 2

findPrime :: Int -> Int -> [Int]

findPrime 0 _ = []

findPrime n x
 | isPrime x [2..floor (sqrt (fromIntegral x))] == False = findPrime n (x + 1)
 | otherwise = [x] ++ findPrime (n-1) (x + 1)

isPrime :: Int -> [Int] -> Bool

isPrime _ [] = True 

isPrime x (y : ys) 
 | x `mod` y == 0 = False
 | otherwise = isPrime x (ys)
```

### Verify whether a list is sorted in ascending order

```py
isSorted :: (Ord a) => [a] -> Bool

isSorted [] = True

isSorted [x] = True

isSorted (x : y : xs) = if x <= y then isSorted (y : xs) else False
```

### Define a function that behaves as : but is defined in terms of ++

```py
myConsRev :: [a]->[a]

myConsRev [] = []

myConsRev (x : xs) = myConsRev(xs) ++ [x]

myCons :: a -> [a] -> [a]

myCons a b = [a] ++ b
```

### Creates a list containing n occurrences of v

```py
occuR :: a -> Int -> [a]

occuR v n = replicate n v
```

### Find all the digits in a string where the prelude function is True on those characters which are digits '0' up to '9' 

```py
dig :: String -> [Bool]

dig [] = []

dig (x : xs) = [x `elem` ['0' .. '9']] ++ dig (xs)
```

### Double all the elements of a list of integers

```py
doubleList :: [Int] -> [Int]

doubleList [] = []

doubleList (x:xs) = (2*x) : doubleList (xs)
```

### Convert all small letters in a string into capitals, leaving the other characters unchanged

```py
import Data.Char

toUpCase :: String -> String

toUpCase [] = []

toUpCase (x : xs) = if isLower x then toUpper x : toUpCase xs
 else x : toUpCase xs
```

### Remove all non-letters from the list

```py
import Data.Char

removeNonL :: String -> String

removeNonL [] = []

removeNonL (x : xs) = if isLetter x then x : removeNonL xs
 else removeNonL xs
```

### Find the list of divisors of a positive integer

```py
divisor :: Int -> [Int]

divisor x = findDiv x [ 1..(x - 1) ]

findDiv :: Int -> [Int] -> [Int]

findDiv x list 
 | length list == 0 = []
 | x `mod` (head list) == 0 = [head list] ++ findDiv x (tail list)
 | otherwise = findDiv x (tail list)
```

### Find all occurrences of an integer n in a list

```py
```

### Find if the element is present in the List 

```py
isElement :: [Int] -> Int -> Bool

isElement [] _ = False

isElement (x:xs) y = if x == y then True
 else isElement (xs) y
```

### Find the sum of lengths of inner lists

```py
lenOfLists :: [[a]] -> Int

lenOfLists [] = 0

lenOfLists x = length(head x) + lenOfLists(tail x)
```
