# tor-request-server

## Requirements

This project requires the user to have Tor installed. Instructions for installing Tor are below.

## Quickstart

```bash
git clone https://github.com/hoganri/tor-request-server  
cd tor-request-server  
npm install  
tor  
npm start  
```

You should see a message in your terminal "Server restarted successfully" indicating that the server has started.

If successful, visit [http://localhost:3100/push?tx=12345](http://localhost:3100/push?tx=12345) and the output will be the response from [Blockstream's hidden service API](https://github.com/Blockstream/esplora/blob/master/API.md) that allows you to broadcast transactions. In this case, it is attempting to broadcast "12345" which is not valid hex, and will therefore display an error message. To use this within your application, pass in the signed transaction hex into the URL parameter - better yet, just use this as a base for your own applications and requests.

## Tor installation

The below is taken from [talmobi's tor-request readme](https://github.com/talmobi/tor-request)


It's highly recommended you run the official client yourself, either locally or otherwise. Tor is available for most systems often just a quick one-line install away.

On **Debian**/**Ubuntu** you can install and run a relatively up to date Tor with.

```bash
apt install tor # should auto run as daemon after install
```

**Misc Linux Command for running Tor as daemon**
`--RunAsDaemon 1`
**thanks @knoxcard**
```
/usr/bin/tor --RunAsDaemon 1
```

On **OSX** you can install with homebrew

```bash
brew install tor
tor # run tor
```

If you'd like to run it as a background process you can add `&` at the end of the command `tor &`. I like to have it running on a separate terminal window/tab/tmux/screen during development in order to see what's going on.

On **Windows** download the tor expert bundle (not the browser), unzip it and run `tor.exe` inside the Tor/ directory.

download link: [Windows Expert Bundle](https://www.torproject.org/download/tor/)

```bash
./Tor/tor.exe # --default-torrc PATH_TO_TORRC
```

See [TorProject.org](https://www.torproject.org/docs/debian.html.en) for detailed installation guides for all platforms.