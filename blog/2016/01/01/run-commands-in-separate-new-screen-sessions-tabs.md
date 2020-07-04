Send commands to tabs in screen.
```sh
screen_name="my_screen"

# Start screen in "detached" mode with a session name.
screen -S "${screen_name}" -t "master" -d -m

# Wait for screen to be ready before opening new sessions.
sleep 1

# Create and send commands to tabs.
screen -S "${screen_name}" -X "screen" -t "my_screen_1"
screen -S "${screen_name}" -p "my_screen_1" -X stuff $'bash script_1.sh\n'

screen -S "${screen_name}" -X "screen" -t "my_screen_2"
screen -S "${screen_name}" -p "my_screen_2" -X stuff $'bash script_2.sh\n'

screen -S "${screen_name}" -X "screen" -t "my_screen_3"
screen -S "${screen_name}" -p "my_screen_3" -X stuff $'bash script_3.sh\n'
```

Quick screen reference
<table>
  <tr>
    <td>Create new window</td>
    <td>Control-a + c</td>
  </tr>
  <tr>
    <td>Next window</td>
    <td>Control-a + n</td>
  </tr>
  <tr>
    <td>Previous window</td>
    <td>Control-a + p</td>
  </tr>
  <tr>
    <td>Detach</td>
    <td>Control-a + d</td>
  </tr>
</table>

List screen sessions
```$ screen -ls
```

Attach to screen
```$ screen -x
```