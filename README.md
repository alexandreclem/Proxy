## Proxy Application using Sockets in C

### What does it do?
The purpose of this project is to present an implementation for unix-based systems of a proxy server that serves a set of clients (concurrently) through parallel programming techniques. The proxy server makes **HTTP** requests to websites over the internet and returns their contents to the clients. The proxy uses a **hash-based cache** to store the contents and have access efficiently.

### Architecture
<p align="center" width="100%">
    <img width="50%" src="https://raw.githubusercontent.com/alexandreclem/Proxy/master/images/img.png">    
</p>

### Application
<p align="center" width="100%">
    <img width="90%" src="https://raw.githubusercontent.com/alexandreclem/Proxy/master/images/img_2.png">    
</p>


### How to run?
- Clone the Repository
    ```bash
    $ git clone https://github.com/alexandreclem/Proxy.git
    ```
- Compile 
    
    - Within the **src/clients** directory, run: 
        ```bash
        $ make
        $ make clean        
        ```
    - Within the **src/proxy** directory, run: 
        ```bash
        $ make
        $ make clean         
        ```
- Execute
    - Within the **src/proxy** directory, run: 
        ```bash    
        $ ./proxy TIMER_LIMIT PROXY_PORT
         ```
        - Where:
            - TMER_LIMIT - Time (in seconds) the data will be stored in the proxy cache
            - PROXY_PORT - Server Port
    
    - Within the **src/clients** directory, run: 
        ```bash    
        $ ./client PROXY_PORT
         ```

> **NOTE**
>
> You can run multiple clients on the same proxy server. For that, make sure the proxy is running and open different terminals to each client and connect them to the server.

### How to use?
- The Data
    - The clients data (.html files) are stored inside **src/clients/data**.
    - The proxy data (.html files) are stored inside **src/proxy/data**.

- Commands 
    In the client CLI you can run the four commands listed below:

    - **fetch**
        - Used to request a website for the proxy. You can pass multiple URL, separated by spaces, for example:
            ```bash
            $ fetch http://www.test.com http://www.test2.com
            ```
            
        
    - **list**
        - Lists the current proxy content. Remember that after the *TIME_LIMIT* set up earlier, all proxy content is erased.
            ```bash
            $ list
            ```

    - **history**
        - Shows the history of commands that were run.
            ```bash
            $ history
            ```
    - **Quit**
        - Bye :)!
            ```bash
            $ quit
            ```

> **NOTE**
>
> In the **src/test_urls.txt** some URLs are provided to test the application.