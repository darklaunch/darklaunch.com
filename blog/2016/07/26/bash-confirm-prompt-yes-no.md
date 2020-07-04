<p>Use an Are you sure? bash prompt for confirmation.</p>

<code name="sh">
read -p "Are you sure you want to continue? [y/n] " -n 1 -r; echo
if [[ $REPLY =~ ^[Yy]$ ]]; then
    echo "Continuing..."
fi
</code>

<p>Ask the inverse by using an exclamation point to negate the if statement.</p>

<code name="sh">
read -p "Continue? [y/n] " -n 1 -r; echo
if ! [[ $REPLY =~ ^[Yy]$ ]]; then
    echo "Stopped"
    exit
fi
</code>