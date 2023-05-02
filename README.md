# pico_TinyGo
This are example code for TinyGo on raspberry pi pico200

# Get Started with TinyGo

## 1. Install Go Programming language
   "https://go.dev/doc/install"

   Remove any previous Go installation by deleting the /usr/local/go folder (if it exists), 
   then extract the archive you just downloaded into /usr/local, creating a fresh Go tree in /usr/local/go:

      $ rm -rf /usr/local/go && tar -C /usr/local -xzf go1.20.3.linux-amd64.tar.gz


   add the following line to your $HOME/.profile or /etc/profile (for a system-wide installation):

      export PATH=$PATH:/usr/local/go/bin
   
   erify that you've installed Go by opening a command prompt and typing the following command:
    
      $ go version

  You're all set!
  
## 2. Install TinyGo(https://tinygo.org/getting-started/overview/)
  
  TinyGo is a new compiler for an existing programming language, the Go programming language. 
  
  If you are using Ubuntu or another Debian based Linux on an Intel processor, 
  download the DEB file from Github and install it using the following   commands:

      wget https://github.com/tinygo-org/tinygo/releases/download/v0.27.0/tinygo_0.27.0_amd64.deb
      sudo dpkg -i tinygo_0.27.0_amd64.deb
   
   You will need to ensure that the path to the tinygo executable file is in your PATH variable.

    export PATH=$PATH:/usr/local/bin
    
   You can test that the installation is working properly by running this code which should display the version number:

    $ tinygo version
    tinygo version 0.27.0 linux/amd64 (using go version go1.20 and LLVM version 1
    
  By using TinyGo you can actually compile and run a binary on a variety of bare metal hardware platforms.
  
      tinygo flash -target=microbit ./main.go
    
## 3. VS Code
  In VS Code, you can edit the file .vscode/settings.json in the root of your project. 
  If the .vscode directory does not yet exist, create it. It’s a normal JSON file where you need to set the go.toolsEnvVars property.
  An example file (again, using the above configuration) is the following:

    {
        "go.toolsEnvVars": {
            "GOROOT": "/home/user/.cache/tinygo/goroot-go1.14-f930d5b5f36579e8cbd1c139012b3d702281417fb6bdf67303c4697195b9ef1f-syscall",
            "GOFLAGS": "-tags=cortexm,baremetal,linux,arm,nrf51822,nrf51,nrf,microbit,tinygo,gc.conservative,scheduler.tasks"
        }
    }
  After creating or modifying this file, you will likely need to restart VS Code to apply these settings.
