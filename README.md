# Hostcheck - Check which hosts are reachable

This shell script performs various tests on the given host names (DNS, ping,
http) to check if they are reachable. It also prints various information about
the network environment.


## Installation

### Manual

Clone this repository and put the `hostcheck` file into a location of your
preference (it should be on your path).

### Using Homebrew

On OS X you can install the script via [Homebrew](https://brew.sh/), from my
personal tap:

```sh
brew tap infogrind/homebrew-tap  # If not already done
brew install hostcheck
```


## Usage

```sh
hostcheck <host> [, <host>, ...]
```

Example:

```sh
hostcheck www.google.com www.asdfxyz123bla.com
```


## Sample Output

```
Environment
----------------------------------------------------------
Wi-Fi network:		acme-office
PROXY:			
http_proxy:		http://proxy.acme.com:3456
https_proxy:		http://proxy.acme.com:3456

Host			DNS	Ping	URL (http)
----------------------------------------------------------
www.google.com		✔	✔	✔
www.asdfxyz123bla.com	✘	-	-
```


## Requirements and Limitations

The script runs on any system that provides the `hostname`, `ping`, and `curl`
commands. If they are not around, or only in a version that does not support the
options used by the script (see the script itself for details), this may result
in error messages in the output.

For displaying the wireless network's SSID, Mac OS is currently required.
