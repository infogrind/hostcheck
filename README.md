# Hostcheck - Check which hosts are reachable

This shell script performs various tests on the given host names (DNS, ping,
http) to check if they are reachable. It also prints various information about
the network environment.


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
Wi-Fi network:		adnovum-office
PROXY:			
http_proxy:		http://proxy.adnovum.hu:3128
https_proxy:		http://proxy.adnovum.hu:3128

Host			DNS	Ping	URL (http)
----------------------------------------------------------
www.google.com		✔	✔	✔
www.asdfxyz123bla.com	✘	-	-
```


## Requirements and Limitations

As I have developed this for myself only, the script currently works properly
only on Mac OS, because of the dependency on Mac OS' Wi-Fi console tool. If run
on another system, as long as that system supports the `host`, `ping`, and
`curl` commands, the output should still be usable, but there will proabably be
an ugly error message in the environment information.

A future release should provide better handling of this.
