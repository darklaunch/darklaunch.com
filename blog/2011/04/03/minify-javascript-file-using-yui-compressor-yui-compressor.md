To minify JavaScript using the YUI Compressor, do the following:

Install YUI Compressor:
```
sudo apt-get install yui-compressor
```

Compress the script:
```
java -jar /usr/share/yui-compressor/yui-compressor.jar --type js -v
myscript.js -o myscript.min.js
```

Your minified script file we be saved to myscript.min.js

---

Posted Apr 3, 2011.
https://www.darklaunch.com/2011/04/03/minify-javascript-file-using-yui-compressor-yui-compressor