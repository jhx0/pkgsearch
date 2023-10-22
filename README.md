# pkgsearch

- pkgsearch is a easy to use tool to search the OpenBSD package repository. 
- pkgsearch downloads the current package index to the local system so as to make a search request fast. This also means searches can be made offline.
- pkgsearch also provides emoji output with the **"-e"** flag.

```
usage: pkgsearch [-h] [-e] [-i] package
```
**Example Output**

![pkgsearch](https://user-images.githubusercontent.com/37046652/200329416-7aedd520-88ae-4a48-a46f-d59801da7be5.png)

## Install

1. Clone/Download the code in this repository
2. Install the necessary dependencies
```
# pkg_add python py3-emoji py3-requests
```
3. Execute (For example):
```
$ ./pkgsearch python3
```

pkgsearch was tested on the current OpenBSD release 7.2 but should also work on older systems.

## Hint
Make sure you set your desired mirror. This can be done by changing the **INDEX_URL** variable in the pkgsearch script.

**Example:**
```
...
INDEX_URL = 'https://ftp.spline.de/pub/OpenBSD/7.2/packages/amd64/index.txt'
...
```
