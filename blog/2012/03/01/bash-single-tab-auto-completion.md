<p>You can tell bash to display possible completions by pressing the tab key only once instead of the usual twice. Add the following to your ~/.inputrc file:</p>

<code name="sh">
# enable single tab completion
set show-all-if-ambiguous on
</code>

<p>You will no longer need to hit the tab key twice to show a list of possible completions.</p>

<p>Additionally, you may want to increase the number of possible completions that may be displayed from the default of 100. Add the following to your ~/.inputrc file:</p>

<code name="sh">
# show more possible completions
set completion-query-items 350
</code>