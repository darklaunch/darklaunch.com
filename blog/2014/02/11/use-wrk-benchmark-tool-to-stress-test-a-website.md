wrk is an HTTP benchmarking tool. https://github.com/wg/wrk

```lua
-- config.lua
wrk.headers["Cookie"] = "sessionid=123; foo=bar"
response = function(status, headers, body)
    for key, value in pairs(headers) do
        if key == "Location" then
            io.write("Location header found!\n")
            io.write(key)
            io.write(":")
            io.write(value)
            io.write("\n")
            io.write("---\n")
            break
        end
    end
end
```

```sh
$ ./wrk \
  --connections="1" \
  --duration="1m" \
  --script="config.lua" \
  --threads="1" \
  "https://www.example.com/"
```

Example wrk scripts: https://github.com/wg/wrk/tree/master/scripts

---

Posted Feb 11, 2014.

https://www.darklaunch.com/2014/02/11/use-wrk-benchmark-tool-to-stress-test-a-website.html