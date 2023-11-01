# pkgsearch

- pkgsearch is a easy to use tool to search the OpenBSD package repository.
- pkgsearch downloads the current package index for defined release (current default = 7.4) to the local system so as to make a search request fast. This also means searches can be made offline.
- pkgsearch also provides emoji output with the **"-e"** flag.

```
usage: pkgsearch [-h] [-e] [-i] [-r RELEASE] [-v] package
```
**Example Output**

![pkgsearch](https://user-images.githubusercontent.com/37046652/200329416-7aedd520-88ae-4a48-a46f-d59801da7be5.png)

## Install

1. Clone/Download the code in this repository
2. Install the necessary dependencies
```
# pkg_add python py3-requests
```
3. Execute (For example):
```
$ ./pkgsearch python3
```
or with emojis displayed:
```
$ ./pkgsearch -e python3
```

You could also search for an older OpenBSD release with `-r` argument:
```
$ ./pkgsearch -r 7.3 vim
```

pkgsearch was tested on the current OpenBSD release 7.4 but should also work on older systems.

## Hint
Make sure you set your desired mirror. This can be done by changing the **INDEX_URL** variable in the pkgsearch script.

**Example:**
```
MIRROR_URL = 'https://ftp.fr.openbsd.org/pub/OpenBSD'
```
## Thanks
- **Laurent Cheylus (https://github.com/lcheylus)** - Code cleanup and improvements (PEP8). Also for improving error handling. Adding the "-v" flag and further improving the code.
- **Cuddle (https://mastodon.bsd.cafe/@cuddle)** and **Laurent Cheylus (https://github.com/lcheylus)** - Cuddle: For improving the codebase and removing the need for a external Python package (Emojis). Laurent Cheylus: For reviewing/creating the PR.
