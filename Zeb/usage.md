## Usage

### Setting Up a New Environment

〉Refer to all script files under all repos and this doc.

Here are the complete steps for setting up the new environment, including the previous steps:


**Start Multiple VLC Instances:**
   - Start one or more VLC instances on each computer, as needed.
   - Ensure that each VLC instance uses the same configuration file, which should include the appropriate settings such as IP addresses and port numbers.

**Start Multiple Nodes:**
   - Start one or more node instances on each computer, as needed.
   - Each node instance should include `znet` and `zchronod`, and should be configured to connect to the PostgreSQL database.

**Configure the Respective Configuration Files:**
   - For each VLC and node instance, ensure that the configuration file contains the correct network settings, database connection information, etc.
   - Individual configuration for each node instance may be required as needed.

**Start the Gateway to Retrieve Data:**
   - Configure the Gateway to connect to your node network.
   - Start the Gateway and ensure that it connects correctly to the nodes and is able to retrieve data.

**Package and Install the Pegion Chrome Extension:**
   - Download the code for the Pegion Chrome extension to your local machine.
   - Package the extension using developer mode and install it in Chrome.
   - Open Chrome, go to the "Extensions" page (chrome://extensions/), and drag and drop the packaged extension file to install it.

**Start Dolphin to View Node Status and Graph Status:**
   - Use your project's Dolphin application to connect to your node network via the web interface.
   - In Dolphin, view the node status and graph status to ensure that the nodes are running correctly and the network connection is proper.

After completing these steps, you should have successfully set up and started the new environment, and should be able to use the Gateway to retrieve data, as well as Dolphin to view node and graph status. If you need further assistance, feel free to ask!
