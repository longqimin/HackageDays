# Data.BitVector
[Data.BitVector @hackage](http://hackage.haskell.org/package/bv)

## Constructor
```haskell
bitVec :: Integral a => Int -> a -> BV
>>> bitVec 3 4 -- [3]4

ones :: Int -> BV
>>> ones 3 -- [3]7

zeros :: Int -> BV
>>> zeros 3 -- [3]0
```

## Selector
###single bit index
```haskell
(@.) :: Integral ix => BV -> ix -> Bool
index :: Integral ix => ix -> BV -> Bool
```

###bits field extraction
```haskell
(@@) :: Integral ix => BV -> (ix, ix) -> BV
extract :: Integral ix => ix -> ix -> BV -> BV
```

## Arithmetic
### concatenation
```haskell
(#) :: BV -> BV -> BV
cat :: BV -> BV -> BV
```
### extending
```haskell
zeroExtend :: Integral size => size -> BV -> BV
signExtend :: Integral size => size -> BV -> BV
```
### list-like operation
```haskell
foldl, foldr, reverse, replicate, and, or, split, group, join
```

### bit wise operation


