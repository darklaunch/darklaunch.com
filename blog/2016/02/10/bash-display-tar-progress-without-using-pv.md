Display progress while creating a tar file.

```bash
tar czf my_file.tar.gz large_file.bin another_large_file.bin &
pid="${!}"

# Stop the tar if this script is killed.
trap "kill ${pid}" EXIT

# Display progress while tar is running.
while kill -0 "${pid}" 2> /dev/null; do
    echo -ne " "$(du my_file.tar.gz)"\r";
    sleep 1
done
```