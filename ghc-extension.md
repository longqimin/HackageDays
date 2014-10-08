# GHC Extensions manual

## GeneralizedNewtypeDeriving

Just as haskell98 knows how to derive those Eq and Show instances for you, you can turn on the GeneralizedNewtypeDeriving extension to ghc to get the Num and Ord instances you need

```haskell
ghci->:set -XGeneralizedNewtypeDeriving
ghci->newtype Foo = Foo Int deriving (Show, Eq, Num, Ord)
ghci->let a = Foo 10
ghci->let b = Foo 5
ghci->a < b -- False
ghci->a + b -- Foo 15
```