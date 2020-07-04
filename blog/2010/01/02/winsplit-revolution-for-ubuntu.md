```
1360x768 monitor:

Top Left:
wmctrl -r :ACTIVE: -b remove,maximized_vert,maximized_horz; wmctrl -r :ACTIVE: -e 1,0,25,672,341

Top:
wmctrl -r :ACTIVE: -b remove,maximized_vert,maximized_horz; wmctrl -r :ACTIVE: -e 1,0,25,1352,327

Top Right:
wmctrl -r :ACTIVE: -b remove,maximized_vert,maximized_horz; wmctrl -r :ACTIVE: -e 1,680,25,672,341

Left:
wmctrl -r :ACTIVE: -b remove,maximized_vert,maximized_horz; wmctrl -r :ACTIVE: -e 1,0,25,676,682

Center (toggle maximize):
handled by keyboard shortcut: "Toggle maximization state"

Right:
wmctrl -r :ACTIVE: -b remove,maximized_vert,maximized_horz; wmctrl -r :ACTIVE: -e 1,676,25,676,682

Bottom Left:
wmctrl -r :ACTIVE: -b remove,maximized_vert,maximized_horz; wmctrl -r :ACTIVE: -e 1,0,366,672,341

Bottom:
wmctrl -r :ACTIVE: -b remove,maximized_vert,maximized_horz; wmctrl -r :ACTIVE: -e 1,0,380,1352,327

Bottom right:
wmctrl -r :ACTIVE: -b remove,maximized_vert,maximized_horz; wmctrl -r :ACTIVE: -e 1,680,366,672,341
```