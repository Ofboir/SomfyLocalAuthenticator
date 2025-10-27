# [DEPRECATED] Somfy Local Authenticator

> [!IMPORTANT]
> This repository is **deprecated**, as the authentication is now available directly in the app. Follow the steps [described here](https://github.com/Somfy-Developer/Somfy-TaHoma-Developer-Mode).

This is a collection of scripts to help authenticate to Somfy Local API. It follows the steps [described here](https://github.com/Somfy-Developer/Somfy-TaHoma-Developer-Mode).

## How to use

The files in this repository are Curl command files, so you need Curl to run them.

```
curl -K command_file.ini
```

The ini extension was chosen only to have nice syntax coloring in VSCodium, but you can change it to anything.

### 1. Login

- Modify `01_Login.ini` :
    - base URL (ha101-1, ha201-1 or ha401-1 ; see [here](https://github.com/Somfy-Developer/Somfy-TaHoma-Developer-Mode?tab=readme-ov-file#api-authentication))
    - userId
    - userPassword
- Launch the command : `curl -K 01_Login.ini`

### 2. Generate a token

- Get the pin of your gateway (eg. 1234-5678-9012). You will find it in your account on Somfy website.
- Modify `02_GenerateToken.ini` :
    - base URL (like in previous step)
    - Pin (part of the URL, in the form XXXX-XXXX-XXXX)
    - JSESSIONID (You will find it in the file `01_cookies.txt` generated at previous step)
- Launch the command : `curl -K 02_GenerateToken.ini`

### 3. Activate your token

- Modify the file `03_body.txt` with the label of your choice and your token (You will find it in the file `02_output.txt` generated at previous step).
- Modify `03_ActivateToken.ini` :
    - base URL and Pin (like in previous step)
    - JSESSIONID (like in previous step)
- Launch the command : `curl -K 03_ActivateToken.ini`
