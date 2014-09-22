# Network.Mail.SMTP Useage
[Network.Mail.SMTP @hackage](http://hackage.haskell.org/package/smtp-mail)

## Establishing Connection
```haskell
ghci->:set -XOverloadedStrings
ghci-> con <- connectSMTP "smtp.163.com"
```

## Authrazition
```haskell
ghci-> login con "long2008920@163.com" password 
```

## Compose Mail
```haskell
ghci-> let from = Address {addressName = Nothing, addressEmail = "long2008920@163.com"}
ghci-> let to = Address {addressName = Nothing, addressEmail = "751738921@qq.com"}
ghci-> let smail = simpleMail from [to] CC BCC "test-mail" [plainPart "hello world"]
```

## Send Mail
```haskell
ghci-> renderAndSend con smail
```

## Note
> mail from address should be the same with smtp server authentication account name, in above tutorial , "long2008920@163.com"