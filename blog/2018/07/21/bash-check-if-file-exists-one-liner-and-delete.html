<p>Delete a file only if it is a regular file without needing to use the force option (-f/--force).</p>

<code name="bash">
set -x

filename="myfile.txt" &&
  ([[ -f "${filename}" ]] && rm --recursive --verbose "${filename}" || exit 0) &&
  echo "done"
</code>

<p>Test the script. First, create the file referenced in the script.</p>

<code name="bash">
$ touch myfile.txt
</code>

<p>Run the script and the file is removed because it is a regular file.</p>

<code name="bash">
$ bash run.sh
+ filename=myfile.txt
+ [[ -f myfile.txt ]]
+ rm --recursive --verbose myfile.txt
removed 'myfile.txt'
+ echo done
done
</code>

<p>Run the script again and the file is not removed because it has already been deleted.</p>

<code name="bash">
$ bash run.sh
+ filename=myfile.txt
+ [[ -f myfile.txt ]]
+ exit 0
+ echo done
done
</code>