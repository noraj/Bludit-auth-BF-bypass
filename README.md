# Bludit Auth BF mitigation bypass exploit / PoC

> Bludit <= 3.9.2 - Authentication Bruteforce Mitigation Bypass

Exploit / PoC for [CVE-2019-17240](https://nvd.nist.gov/vuln/detail/CVE-2019-17240).

## Usage

```
$ ruby exploit.rb --help
Bludit <= 3.9.2 - Authentication Bruteforce Mitigation Bypass

Usage:
  exploit.rb -r <url> -u <username> -w <path> [--debug]
  exploit.rb -H | --help

Options:
  -r <url>, --root-url <url>            Root URL (base path) including HTTP scheme, port and root folder
  -u <username>, --user <username>      Username of the admin
  -w <path>, --wordlist <path>          Path to the wordlist file
  --debug                               Display arguments
  -H, --help                            Show this screen

Examples:
  exploit.rb -r http://example.org -u admin -w myWordlist.txt
  exploit.rb -r https://example.org:8443/bludit -u john -w /usr/share/wordlists/password/rockyou.txt
```

## Requirements

- [httpclient](https://github.com/nahi/httpclient)
- [docopt.rb](https://github.com/docopt/docopt.rb)

Example for BlackArch:

```
pacman -S ruby-httpclient ruby-docopt
```

Example using gem:

```
gem install httpclient docopt
```

## Reference

This is an exploit for the vulnerability found by [Rastating](https://rastating.github.io/) on [Bludit CMS](https://www.bludit.com/).

Vulnerability explanation: https://rastating.github.io/bludit-brute-force-mitigation-bypass/.

Patch: https://github.com/bludit/bludit/pull/1090

This exploit was tested with Ruby 2.7.1.
