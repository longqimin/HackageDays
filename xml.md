# Text.XML.Light Usage
[Text.XML.Light @hackage](http://hackage.haskell.org/package/xml-1.3.13)

## Import Text.XML.Light modules
```haskell
import Text.XML.Light.Input
import Text.XML.Light.Proc
import Text.XML.Ligth.Types
```

## Read your XML source file
```haskell
ghci-> input <- readFile "new.xml"
```
```
<?xml version="1.0"?>
<!-- new.xml -->
<note>
  <from>John</from>
  <to>George</to>
  <message>French aaa</message>
</note>
```
## Parse Input String
```haskell
ghci-> let contents = parseXML input :: [Content]
ghci-> let elem = parseXMLDoc input :: Maybe Element
```

## Process XML Element or Content or Attributes
```haskell
ghci-> let name = QName {qName = "from", qURI = Nothing, qPrefix = Nothing}
ghci-> findChild name elem :: Maybe Element
```