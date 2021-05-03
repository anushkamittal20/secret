# 

Create a package that will store secrets - things like API keys - in an encrypted file. Then create a CLI that will make it possible to set and get these secrets via the command line as well.

*The CLI should mostly just be a wrapper around the `secret` package you create that uses a secrets file in your home directory. For more info on creating a CLI or finding the home directory on different OSes see the [task exercise](https://gophercises.com/exercises/task).*

The way developers use the final version of the `secret` package should look something like this:

```go
v := secret.FileVault("encoding-key", "path/to/file")
err := v.Set("key-name", "key-value")
value, err := v.Get("key-name")
fmt.Println(value) // "key-value"
```



*The crypto code used in this exercise is based heavily on the code in the standard library's [CFB Encrypter](https://golang.org/pkg/crypto/cipher/#NewCFBEncrypter) and [CFB Decrypter](https://golang.org/pkg/crypto/cipher/#NewCFBDecrypter) examples.*

The CLI usage should probably end up looking like this:

```bash
$ secret set twitter_api_key "some value here" -k "your-encoding-key"
# Value set!
secret get twitter_api_key -k "your-encoding-key"
# "some value here"
```

You can either provide the key via a flag, or have your program read it via an environment variable. 





go build -o ./secrets cmd/cli.go && ./secret set twitter_api_key "some-value"
./secret get twitter_api_key                                                 
./secret set demo abc123       
 ./secret get demo  