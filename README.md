# 

A package that will store secrets - things like API keys - in an encrypted file and a CLI that will make it possible to set and get these secrets via the command line as well.




*The crypto code used in this exercise is based heavily on the code in the standard library's [CFB Encrypter](https://golang.org/pkg/crypto/cipher/#NewCFBEncrypter) and [CFB Decrypter](https://golang.org/pkg/crypto/cipher/#NewCFBDecrypter) examples.*


vault.go deals with most of the encryption and decryption and cipher.go deals with setting up of you cli.


To execute try cloning the repository and running the following in the terminal
```
go build -o ./secrets cmd/cli.go && ./secret set twitter_api_key "some-value"
./secret get twitter_api_key                                                 
./secret set demo abc123       
 ./secret get demo  
 ```
