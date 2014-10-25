# Data.Aeson

{-# LANGUAGE DeriveGeneric #-}

import Data.Aeson
import GHC.Generics

data Person = Person String String Int  | Unknown String deriving (Show, Eq, Generic)

instance ToJSON Person

instance FromJSON Person
