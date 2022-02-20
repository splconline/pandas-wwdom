# How to Install GitHub Desktop on Linux Mint (Ubuntu etc.)

*Instructions below courtesy of [this page](https://gist.github.com/berkorbay/6feda478a00b0432d13f1fc0a50467f1).*

Go to [this github page](https://github.com/shiftkey/desktop/releases) and figure out what the latest version is, and the path of the .deb download URL. As of 20.02.2022, the latest version was 2.9.6, and the .deb download URL was `https://github.com/shiftkey/desktop/releases/download/release-2.9.6-linux1/GitHubDesktop-linux-2.9.6-linux1.deb`.

So get it:
```
sudo wget https://github.com/shiftkey/desktop/releases/download/release-2.9.6-linux1/GitHubDesktop-linux-2.9.6-linux1.deb
```
If `gdebi-core` isn't there, install it:
```
sudo apt-get install gdebi-core 
```
Then install GitHub Desktop:
```
sudo gdebi GitHubDesktop-linux-2.9.6-linux1.deb
```
