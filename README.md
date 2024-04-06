# pkgsearch

- pkgsearch is a easy to use tool to search the OpenBSD package repository.
- pkgsearch downloads the current package index for defined release (current default = 7.5) or snapshots and defined architecture (default = amd64) to the local system so as to make a search request fast. This also means searches can be made offline.
- pkgsearch also provides emoji output with the **"-e"** flag.

```
usage: pkgsearch [-h] [-e] [-i] [-r RELEASE | -s] [-a ARCH] [-v] package

positional arguments:
  package

options:
  -h, --help            show this help message and exit
  -e, --emoji           turn on emoji output
  -i, --index           download index
  -r RELEASE, --release RELEASE
                        release to search for packages (default = 7.5)
  -s, --snapshot        search for packages in snapshots
  -a ARCH, --arch ARCH  arch to search for packages (default = amd64)
  -v, --version         display version
```
**Example Output**

![pkgsearch](https://user-images.githubusercontent.com/37046652/200329416-7aedd520-88ae-4a48-a46f-d59801da7be5.png)

## Install

1. Clone/Download the code in this repository
2. Install the necessary dependencies
```
# pkg_add python py3-requests py3-packaging
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
$ ./pkgsearch -r 7.4 vim
```

pkgsearch was tested on the current OpenBSD release 7.5 but should also work on older systems.

## Hint
Make sure you set your desired mirror. This can be done by changing the **INDEX_URL** variable in the pkgsearch script.

**Example:**
```
MIRROR_URL = 'https://ftp.fr.openbsd.org/pub/OpenBSD'
```
## Thanks
- **Laurent Cheylus (https://github.com/lcheylus)** - Code cleanup and improvements (PEP8). Also for improving error handling. Adding the "-v" flag and further improving the code. Adding the "-r" option and improving the code further. Adding the "-s" (snapshot) option. Adding the "-a" (Arch) option. Refining the code and providing fixes.
- **Cuddle (https://mastodon.bsd.cafe/@cuddle)** and **Laurent Cheylus (https://github.com/lcheylus)** - Cuddle: For improving the codebase and removing the need for a external Python package (Emojis). Laurent Cheylus: For reviewing/creating the PR.
- **Alexander Naumov** (https://github.com/alexander-naumov) - Suggestions regarding debugging.
