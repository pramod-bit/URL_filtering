# HTTP Proxy Server

## Overview

This is a simple HTTP proxy server written in C. It allows you to compile and run a proxy server that can be configured to listen on a specified port. The server supports blocking specific URLs, maintains a blocklist, and caches responses from target servers.

## Usage

1. **Compile the Proxy Server Code:**

    ```bash
    gcc -o HTTP_Proxy HTTP_Proxy.c
    ```

2. **Run the Compiled Binary:**

    - To specify a port number:
        ```bash
        ./HTTP_Proxy -p <port_number>
        ```

    - If no port number is specified, the program prompts you to enter one.

3. **Blocking URLs:**

    - Add a URL to the blocklist:
        ```bash
        Enter a command (a - add, r - remove, l - list, q - quit): a
        Enter the URL to block: www.example.com
        ```

    - Remove a URL from the blocklist:
        ```bash
        Enter a command (a - add, r - remove, l - list, q - quit): r
        Enter the URL to remove: www.example.com
        ```

    - List blocked URLs:
        ```bash
        Enter a command (a - add, r - remove, l - list, q - quit): l
        ```

4. **Cache:**

    - The proxy server caches responses from target servers. The cache size is limited to 10 entries.

5. **Quitting:**

    - Quit the proxy server:
        ```bash
        Enter a command (a - add, r - remove, l - list, q - quit): q
        ```

# Blocklist File

The list of blocked URLs is stored in a file named `Blocklist.txt` in the same directory as the proxy server program. The blocklist is saved to this file whenever a URL is added or removed. The proxy server also loads the blocklist from this file when it starts.

## HTTP Blocklist:
- example.net
- example.com
- sneaindia.com

## HTTPS Blocklist:
- www.youtube.com
- www.google.com
- www.github.com

## URL Blocklist File

This file contains a list of URLs to be blocked by the HTTP/HTTPS proxy server.

**Instructions for Adding URLs:**
Each URL must be listed on a separate line. URLs should be written in the following format:
**Correct Format:** `www.example.com`
**Incorrect Format:** `"www.example.com"` (Avoid using quotes)

**Example:**

**Explanation:**
The `.txt` file serves as a blocklist for the proxy server. Each URL to be blocked is listed on a separate line without any additional characters like quotes. Proper formatting (`www.example.com`) ensures that the proxy server accurately recognizes and blocks the specified URLs. To add more URLs to the blocklist, simply follow the instructions outlined above. Remember to save the file after making any changes.

This file is directly read by the C code implementation of the proxy server, ensuring that the listed URLs are effectively blocked.

## Note

This is a basic implementation, and you may need to customize it based on your requirements.

Feel free to explore and modify the code as needed. If you encounter any issues or have suggestions for improvements, please [open an issue](https://github.com/your-username/your-repository/issues).
