# Somfy Local Authenticator

This is a collection of scripts to help authenticate to Somfy Local API. It follows the steps [described here](https://github.com/Somfy-Developer/Somfy-TaHoma-Developer-Mode).

## How to use

The files in this repository are Curl command files, so you need Curl to run them.

```
curl -K command_file.ini
```

The ini extension was chosen only to have nice syntax coloring in VSCodium, but you can change it to anything.

Some of the data in the files must be overwritten with your own :

01_Login
- base URL (ha101-1, ha201-1 or ha401-1 ; see [here](https://github.com/Somfy-Developer/Somfy-TaHoma-Developer-Mode?tab=readme-ov-file#api-authentication))
- userId
- userPassword

02_GenerateToken
- base URL (ha101-1, ha201-1 or ha401-1 ; see [here](https://github.com/Somfy-Developer/Somfy-TaHoma-Developer-Mode?tab=readme-ov-file#api-authentication))
- Pin (part of the URL, in the form XXXX-XXXX-XXXX)
- JSESSIONID

03_ActivateToken
- base URL (ha101-1, ha201-1 or ha401-1 ; see [here](https://github.com/Somfy-Developer/Somfy-TaHoma-Developer-Mode?tab=readme-ov-file#api-authentication))
- Pin (part of the URL, in the form XXXX-XXXX-XXXX)
- JSESSIONID

### How to get your Pin ?

Simply log to Somfy website, you will find it on your account.

### How to get your JSESSIONID ?

You will get it in the cookies of the first step. Simply open the file `01_cookies.txt` generated and copy the whole string after `JSESSIONID`.