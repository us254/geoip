First, use the command 'curl' to download a file called 'go.tar.gz' which contains the Go programming language. Then, extract the contents of the file to the directory '/usr/local', and set the PATH environment variable to include the location of the Go executable. Check that the installation was successful by running the command 'go version'. 
 
Next, download a file called 'config.json' from GitHub using the 'wget' command. This file contains a piece of code that includes a list of IPv4 addresses in Iran in CIDR format. You can find this list on the website 'ip2location.com' under 'visitor-blocker'. The code also specifies the file 'IRip.txt' which contains the list of addresses. Once the code is executed, the output file 'geoip.dat' will be created, which will contain information about the Iran IP addresses.

The steps followed to create files like this are:
 1. Download the Go programming language by running the following commands in the terminal:
   -  `curl -sLo go.tar.gz https://go.dev/dl/go1.20.1.linux-amd64.tar.gz` 
   -  `tar -C /usr/local -xzf go.tar.gz` 
   -  `rm go.tar.gz` 
2. Clone the geoip repository from GitHub by running the following command in the terminal:
   -  `git clone https://github.com/Loyalsoldier/geoip.git` 
3. Navigate to the geoip directory by running the following command in the terminal:
   -  `cd geoip` 
4. Remove the existing config.json file by running the following command in the terminal:
   -  `rm -f config.json` 
5. Download the updated config.json file from GitHub by running the following command in the terminal:
   -  `wget https://raw.githubusercontent.com/us254/geoip/master/config.json` 
6. Run the Go program in the terminal to generate the updated geoip.dat file:
   -  `go run .` 
 The config.json file contains the following code:
```

{
  "input": [
    {
      "type": "text",
      "action": "add",
      "args": {
        "name": "ir",
        "uri": "https://raw.githubusercontent.com/us254/geoip/master/k/IRip.txt",
        "onlyIPType": "ipv4"
      }
    }
  ],
  "output": [
    {
      "type": "v2rayGeoIPDat",
      "action": "output",
      "args": {
        "outputName": "geoip.dat",
        "wantedList": [
          "ir"
        ]
      }
    }
  ]
}

```
The "uri": ` "https://raw.githubusercontent.com/us254/geoip/master/IRip.txt" ` line inside the config.json file points to the IRip.txt file that contains a list of Iran's IP addresses in CIDR format. This list can be obtained from the website ` https://www.ip2location.com/free/visitor-blocker `.
 Here are some examples of the CIDR codes from IRip.txt file:
```
 - 2.144.0.0/14
  (This block contains IP addresses from 2.144.0.0 to 2.147.255.255)
 - 2.176.0.0/12
  (This block contains IP addresses from 2.176.0.0 to 2.191.255.255)
 - 5.1.43.0/24
  (This block contains IP addresses from 5.1.43.0 to 5.1.43.255)
 - 5.22.0.0/17
  (This block contains IP addresses from 5.22.0.0 to 5.23.255.255)
 - 5.22.192.0/21
  (This block contains IP addresses from 5.22.192.0 to 5.22.207.255)
 - 5.22.200.0/22
  (This block contains IP addresses from 5.22.200.0 to 5.22.203.255)
```
