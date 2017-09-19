## Compiling and running Breeze Wallet
If you prefer to compile and run everything yourself, please follow these steps closely.

## Install and run TOR
To ensure greater privacy while running the Breeze Wallet we enforce running tor.<br />
Follow the instructions for your operating system below.<br />
Note that you will have to run TOR each time you want to start the wallet.<br />

**Windows**<br />
Download and install the TOR Expert Bundle for Windows at: [torproject.org](https://www.torproject.org/download/download.html.en)<br />
Unzip the Expert Bundle and create a Windows Batch file in the Tor folder, containing:
```
tor -controlport 9051 -cookieauthentication 1
```

Run the batch file (run this each time you want to start the wallet).

**macOS** <br />
Install homebrew
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Install TOR
```
brew install tor
```

Start TOR (run this each time you want to start the wallet)
```
tor -controlport 9051 -cookieauthentication 1
```

**Debian/Ubuntu** <br />
Install TOR
```
sudo apt-get install tor
```

Run TOR (run this each time you want to start the wallet)
```
tor -controlport 9051 -cookieauthentication 1
```

## .NET Core 1.0.5 & 1.1.2 SDK 1.0.4

Download your version for your OS from this page (https://github.com/dotnet/core/blob/master/release-notes/download-archives/1.1.2-download.md) before you clone the Breeze wallet

## Compile and run the Daemon
How to build and run Breeze Wallet

To build breeze wallet with Breeze Privacy Protocol, you need to first build and run Breeze Daemon.

Breeze daemon is the backend REST service, hosting a Bitcoin node upon which Breeze UI depends:

```
# Clone and go in the directory
git clone https://github.com/breezehub/Breeze
cd Breeze

#change to required branch
git checkout tumblebit-alpha

# Initialize dependencies
git submodule update --init --recursive

# Go in Breeze's solution folder
cd Breeze
dotnet restore
dotnet build

# Run a daemon Bitcoin SPV node on testnet with tumblebit
cd src/Breeze.Daemon
dotnet run light -testnet -tumblebit -ppuri=ctb://pmkdcyilefpi2aal.onion?h=aa4e984c5655a677716539acc8cbc0ce29331429
```

To build the client:

Open a new terminal and navigate to the Breeze UI folder:
``` bash
cd ./Breeze/Breeze.UI
```

## Install dependencies with npm:

From within Breeze.UI directory run:

``` bash
npm install
```

To run the app in debug mode:

```
npm start
```

## To build for production

- Using development variables (environments/index.ts) :  `npm run electron:dev`
- Using production variables (environments/index.prod.ts) :  `npm run electron:prod`

Enjoy and please give us [feedback](https://stratisplatform.slack.com/messages/C5F5GGLC8/), [contribute](https://github.com/BreezeHub) and join us on the [slack](https://stratisplatform.slack.com/messages/C5F5GGLC8/).

