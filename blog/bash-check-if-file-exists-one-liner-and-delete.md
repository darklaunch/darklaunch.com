Delete a file only if it is a regular file without needing to use the force option (-f/--force).
```bash
set -x

filename="myfile.txt" &&
  ([[ -f "${filename}" ]] && rm --recursive --verbose "${filename}" || exit 0) &&
  echo "done"
```

Test the script. First, create the file referenced in the script.
```bash
$ touch myfile.txt
```

Run the script and the file is removed because it is a regular file.
```bash
$ bash run.sh
+ filename=myfile.txt
+ [[ -f myfile.txt ]]
+ rm --recursive --verbose myfile.txt
removed 'myfile.txt'
+ echo done
done
```

Run the script again and the file is not removed because it has already been deleted.
```bash
$ bash run.sh
+ filename=myfile.txt
+ [[ -f myfile.txt ]]
+ exit 0
+ echo done
done
```