 Here is a step-by-step guide to install the Go programming language, clone the geoip repository, and generate the `geoip.dat` file using the provided configuration.

### Step-by-Step Guide

#### Step 1: Update the System and Install Git
1. **Update the package list:**
   ```bash
   sudo apt-get update
   ```
2. **Install Git:**
   ```bash
   sudo apt-get install git
   ```
3. **Verify Git installation:**
   ```bash
   git --version
   ```

#### Step 2: Install the Go Programming Language
1. **Download the Go tarball:**
   ```bash
   curl -sLo go.tar.gz https://go.dev/dl/go1.22.3.linux-amd64.tar.gz
   ```
2. **Extract the tarball to `/usr/local`:**
   ```bash
   sudo tar -C /usr/local -xzf go.tar.gz
   ```
3. **Remove the tarball:**
   ```bash
   rm go.tar.gz
   ```
4. **Set the PATH environment variable:**
   ```bash
   export PATH=$PATH:/usr/local/go/bin
   ```
5. **Verify Go installation:**
   ```bash
   go version
   ```

#### Step 3: Clone the geoip Repository
1. **Clone the repository:**
   ```bash
   git clone https://github.com/us254/geoip.git
   ```
2. **Navigate to the geoip directory:**
   ```bash
   cd geoip
   ```

#### Step 4: Update the Configuration File
1. **Remove the existing `config.json` file:**
   ```bash
   rm -f config.json
   ```
2. **Download the updated `config.json` file:**
   ```bash
   wget https://raw.githubusercontent.com/us254/geoip/master/config.json
   ```

#### Step 5: Run the Go Program to Generate `geoip.dat`
1. **Run the Go program:**
   ```bash
   go run .
   ```

### Configuration File (`config.json`)
The `config.json` file should contain the following code:
```json
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

### Summary
1. **Update System and Install Git:**
   ```bash
   sudo apt-get update
   sudo apt-get install git
   git --version
   ```

2. **Install Go Programming Language:**
   ```bash
   curl -sLo go.tar.gz https://go.dev/dl/go1.20.5.linux-amd64.tar.gz
   sudo tar -C /usr/local -xzf go.tar.gz
   rm go.tar.gz
   export PATH=$PATH:/usr/local/go/bin
   go version
   ```

3. **Clone geoip Repository:**
   ```bash
   git clone https://github.com/us254/geoip.git
   cd geoip
   ```

4. **Update Configuration File:**
   ```bash
   rm -f config.json
   wget https://raw.githubusercontent.com/us254/geoip/master/config.json
   ```

5. **Generate `geoip.dat`:**
   ```bash
   go run .
   ```

### Example Commands
```bash
# Update System and Install Git
sudo apt-get update
sudo apt-get install git
git --version

# Install Go Programming Language
curl -sLo go.tar.gz https://go.dev/dl/go1.20.5.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go.tar.gz
rm go.tar.gz
export PATH=$PATH:/usr/local/go/bin
go version

# Clone geoip Repository
git clone https://github.com/us254/geoip.git
cd geoip

# Update Configuration File
rm -f config.json
wget https://raw.githubusercontent.com/us254/geoip/master/config.json

# Generate geoip.dat
go run .
```

By following these steps, you can install the Go programming language, clone the geoip repository, update the configuration file, and generate the `geoip.dat` file.
