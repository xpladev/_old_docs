---
weight: 50
title: "'xplad' Mac"
---

# Install `xplad` for Mac (Intel or M1)

`xplad` is the command-line interface and daemon that connects to Xpla and enables you to interact with the Xpla blockchain. Xpla core is the official Golang reference implementation of the Xpla node software.

This guide is for developers who want to install `xplad` and interact with Xpla core without running a full node. If you want to run a full node or join a network, visit [Run a Full Xpla Node]({{< ref "run-a-full-xpla-node" >}}).

1. Navigate to [https://github.com/c2xdev/core/tags](https://github.com/c2xdev/core/tags) and click on the latest release. 

2. Download the `xpla_<latest-version-here>_Darwin_x86_64.tar.gz` file.

3. Unzip the file in the downloads folder by double clicking on it. 

   {{< hint danger >}}
   **M1 and M2 Mac users**  
   If you are using an Intel-based Mac, proceed to step 4. 
   
   M1 Mac users will need to create `/lib` and `/bin` directories in `/usr/local`:
   
   ```sh
   sudo cd /usr/local
   sudo mkdir lib
   sudo mkdir bin
   ```
   {{< /hint >}}

4. Navigate to the expanded file in downloads: 
    
   ```sh
   cd Downloads/xpla_<downloaded-version>_Darwin_x86_64/
   ```
    
5. Copy `libwasmvm.dylib` to `/lib`:

   ```sh
   sudo cp libwasmvm.dylib /usr/local/lib
   ```


6. Add `xplad` to your path:

   ```sh
   sudo cp xplad /usr/local/bin
   ```


7. Start `xplad`

   ```sh
   xplad
   ```
   {{< hint info >}}
   **If a security warning occurs:**  
   1. Open your System Preferences and click **Security & Privacy**. 
   2. Under the **General** tab, click **Allow anyway**.
   3. Run `xplad` again. 
   4. When prompted, click **Open**.
   5. Repeat for other security errors or warnings. 
   {{< /hint >}}
