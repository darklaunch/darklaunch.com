To run a script or set of commands from a remote website, do the following:

```bash
bash < <(curl --silent https://www.example.com/path/to/script.sh)
```

This will cause curl to pull the script and redirect its contents to stdin for bash to parse.

NOTE: be careful with this

---


Posted Aug 11, 2012.
https://www.darklaunch.com/2012/08/11/bash-run-script-on-web-page-from-url.html