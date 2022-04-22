# Byobu save text

Save screen scrollback history text in Byobu using a shortcut:

`Shift` + `F7`

---

Posted Sep 11, 2019.

https://www.darklaunch.com/2019/09/11/byobu-save-text.html

---

3 comments

<ol><li><div>

Zach &ndash; Jan 21, 2021<div>

If the keyboard shortcuts are not working, try this:

`Ctrl` + `a`, then enter the following command to save the pane's full text and not just the visible text:

`:capture-pane -S - -E -; save-buffer "$BYOBU_RUN_DIR/printscreen"`

Then you can view the captured text of the pane:
`$ vim $BYOBU_RUN_DIR/printscreen`

</div></div><ol><li><div>

anonymous &ndash; Jan 21, 2021<div>

see also `man tmux` for info on `capture-pane`

</div></div></li></ol></li><li><div>

ak &ndash; Apr 1, 2022<div>

Magnificent!  Works as stated.

I'm using BYOBU via Conda on CentOS 7 (in order to get version 5.133) and Shift+F7 wouldn't work as I have no idea where BYOBU_RUN_DIR is located nor how to determine where that setting it set.  I even ran `updatedb` then searched for `locate -ir printscreen$` which returned nothing.

Thank you.

</div></div></li></ol>