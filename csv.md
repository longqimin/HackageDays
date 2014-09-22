# Data.Csv
[Data.Csv](http://hackage.haskell.org/package/cassava-0.4.1.0) @hackage

## custome data type
```haskell
import Control.Applicative
import Data.Csv
import Data.Text (Text)
import Data.Vector hiding (empty)
import Prelude hiding (length)

data Person = Person {name = !Text, age = !Int} deriving (Show)
```

## encode 

```haskell
instance ToRecord Person where
	toRecord (Person name age) = vector [toField name, toField age]
```

## decode
```haskell
instance FromRecord Person where
	parseRecord v 
		| length v == 2 = Person <$> 
						  v .! 0 <*>
						  v .! 1
		| otherwise = empty
```

## test
```haskell
ghci-> let a = Person "John" 18
ghci-> encode [a] -- "john,18\r\n"

ghci-> decode NoHeader "john, 18" :: Either String (Vector Person) -- Right (fromList [Person {name = "john", age = 18}])
```
