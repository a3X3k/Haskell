<div align = "center">

# [Haskell Programming](#)
  
</div>

### Convert Integer to Double

```py
double :: Int -> Double

double x = y
 where y = fromIntegral x :: Double 
```

### Take an integer input and return the the next integer as input which is the next integer number.

```py
successor :: Int -> Int

successor x = x + 1
```

### Take an integer and return a boolean value True if even else False

```py
evenBool :: Int -> Bool

evenBool x = if x `mod` 2 == 0 then True else False
```

```py
evenBool' x | x `mod` 2 == 0 = True
            | otherwise = False
```

### Find the absolute of a number n

```py
abs' :: Int -> Int

abs' x = if x >= 0 then x else -x
```

```py
abs'' :: Int -> Int

abs'' x | x >= 0 = x
        | otherwise = -x
```

### Find the Power of n

```py
power :: Float -> Int -> Float

power _ 0 = 1

power x n = x * (power x (n-1))
```

### Find Leap Year or Not

```py
leap :: Int -> String

leap x | x `mod` 4 == 0 && x `mod` 10 /= 0 = "It's a Leap Year!"
 | x `mod` 400 == 0 = "It's a Leap Year!"
 | otherwise = "It's not a Leap Year!"
```

### Calculate |c| = √(x2 + y2)

```py
complexNumber :: Float -> Float -> Float

complexNumber x y = ( x * x + y * y ) ** (1/2)
```

### Convert Bool to Int & Int to Bool

```py
boolToInt :: Bool -> Int

boolToInt x | x == True = 1
 | otherwise = 0
```

```py
intToBool :: Int -> Bool

intToBool x | x == 0 = False
 | otherwise = True
```

### Find the largest of 2 numbers

```py
maxof2 :: (RealFloat x) => x -> x -> x

maxof2 x y | x >= y = x
 | otherwise = y
```

### Find the largest of 3 numbers

```py
max3 :: (RealFloat x) => x -> x -> x -> x

max3 x y z = 

 if (x >= y) && (x >= z) then x
 else if (y >= x) && (y >= z) then y
 else z 
```

### Find Even or Odd

```py
evenodd :: Int -> String

evenodd x = if x `mod` 2 == 0 then "Even" else "Odd"
```

### Find the distance between two points in a xy-plane. Let P = (x1, y1) and Q = (x2, y2).

```py
dist :: (RealFloat x) => x -> x -> x -> x -> x

dist x1 y1 x2 y2 = sqrt((a)^2 + (b)^2) where 
 a = x2 - x1      
 b = y2 - y1
```

### Find Min or Max

```py
min1 :: (Ord a) => a -> a -> a

min1 x y | x < y = x
 | otherwise = y


max1 :: (Ord a) => a -> a -> a

max1 x y | x > y = x
 | otherwise = y
```

### Verify whether the first argument divides the second one. 

```py
divides :: Int -> Int -> Bool

divides 0 _ = False

divides x y = y `mod` x == 0

divide :: Int -> Int -> Bool

divide x y = if x == 0 then False
 else if y `mod` x == 0 then True
 else False

divi :: Int -> Int -> Bool

divi x y | x == 0 = False
 | y `mod` x == 0 = True
 | otherwise = False
```

### Implement Stirling’s formula

```py
stirling :: Int -> Float

stirling x = sqrt ( 2 * pi * a ) * ( (a / exp 1) ** a ) where
 a :: Float
 a = fromIntegral x
```

### Find the number of solution of a quadratic equation

```py
noOfSol :: Int -> Int -> Int -> String

noOfSol a b c | sol > 0 = "2 Solutions"
 | sol == 0 = "1 Solution"
 | otherwise = "No Solution" where
 sol = (b * b) - (4 * a * c)
```

### Find the two roots of a Quadratic equation

```py
rootsOfQuadraticEqu :: (Float, Float, Float) -> (Float, Float)

rootsOfQuadraticEqu (a, b, c) = (x, y) where
 x = eq + sqrt root / ( 2 * a )
 y = eq - sqrt root / ( 2 * a )
 eq = - b / (2 * a)
 root = ( b * b ) - ( 4 * a * c )
```

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
indexL :: [Int] -> Int -> [Int]

indexL list x = findOcc list x 0

findOcc :: [Int] -> Int -> Int -> [Int]

findOcc [] _ _ = []

findOcc (x:xs) ele i = if x == ele then [i] ++ findOcc xs ele (i + 1)
 else findOcc xs ele (i + 1)
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

### Define a function that maps a positive integer to its list of factors

```py
factor :: Int -> [Int]

factor y = [ x | x <- [1 .. y], y `mod` x == 0]
```

### Define a function that returns the list of all prime numbers up to a given limit n

```py
isPrime :: Int -> Bool

isPrime n = null [i | i <- [2 .. floor (sqrt (fromIntegral n))], n `mod` i == 0]

nPrime :: Int -> [Int]

nPrime n = [x | x <- [2 .. n], isPrime x]
```

### Define a function pairs that uses the zip function for returning the list of all pairs of adjacent elements from a list

```py
pairs :: [a] -> [(a, a)]

pairs x = zip x (tail x)
```

### Define a function sorted that decides if the elements in a list are sorted [ Checking the list which is formed by pair function ]

```py
pair :: [a] -> [(a, a)]

pair x = zip x (tail x)

sortF :: (Ord a) => (a, a) -> Bool

sortF (x,y) = if x <= y then True else False

sorted :: (Ord a) => [a] -> Bool

sorted x = null [ i | i <- (pair x), sortF i == False]
```

### Define a function positions using zip function which will return the list of all positions of a value in a list

```py
positions :: Eq a => [a] -> a -> [Int]

positions list x = [i | (i, j) <- zip [0 .. ] list, j == x]
```

### Define a function count to get the number of times a character occurs in a String

```py
count :: (Ord a) => [a] -> a -> Int

count list x = length [ i | i <- list, i == x ]
```

### Consider a triple (x,y,z) of positive integers called pythagorean if x^2 + y^2 = z^2. 

```py
pythagorean :: Int -> [(Int, Int, Int)]

pythagorean n = [ (x, y, z) | x <- [ 1.. n ], y <- [ 1 .. n ], z <- [ 1 .. n ], ( x^2 + y^2 == z^2 ) ]
```

### A perfect number is a positive integer which is equal to the sum of all its factors, excluding the number itself. Using list comprehension, define a function perfects :: Int->Int that returns all the perfect numbers up to a given limit n.

```py
fact :: Int -> [Int]

fact x = [ i | i <- [ 1 .. (x - 1) ], x `mod` i == 0]


sumOfF :: [Int] -> Int

sumOfF [] = 0

sumOfF ( x : xs ) = x + sumOfF xs


perfect :: Int -> [Int]

perfect n = [ i | i <- [ 1 .. n ], sumOfF (fact i) == i]
```

### Define a function scalar to find the scalar product of list elements of two lists xs and ys of length n

```py
scalarP :: [Int] -> [Int] -> [Int]

scalarP x y = [ i * j | ( i, j ) <- zip x y ]
```

### Define the function sumsq, which takes an integer n as its argument and returns the sum of the squares of the first n integers

```py
sumSQ :: Int -> Int

sumSQ n = sum [ i*i | i <- [ 1 .. n ] ]
```

### Convert every character in string to uppercase and remove any digits in it

```py
import Data.Char

charToUp :: String -> String

charToUp string = [ toUpper i | i <- string, i `elem` [ 'a' .. 'z' ] || i `elem` [ 'A' .. 'Z' ] ]
```

### Define a function that extracts the upper case letters only

```py
extractUpper :: String -> String

extractUpper string = [ i | i <- string, isUpper i] 
```

### Define a function that will capitalize the first letter of a String and return the entire String

```py
caps :: String -> String

caps string = toUpper (head string) : tail string
```

### Define a function cpy to make a string of n characters

```py
cpy :: Char -> Int -> String

cpy c n = replicate n c
```

### Define a function to place space characters between characters in a string

```py
space :: String -> String

space ( x : xs )
 | length(xs) == 0 = x : ""
 | otherwise = x : " " ++ space xs 
```
