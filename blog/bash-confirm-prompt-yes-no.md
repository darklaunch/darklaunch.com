Use an Are you sure? bash prompt for confirmation.
```sh
read -p "Are you sure you want to continue? [y/n] " -n 1 -r; echo
if [[ $REPLY =~ ^[Yy]$ ]]; then
    echo "Continuing..."
fi
```

Ask the inverse by using an exclamation point to negate the if statement.
```sh
read -p "Continue? [y/n] " -n 1 -r; echo
if ! [[ $REPLY =~ ^[Yy]$ ]]; then
    echo "Stopped"
    exit
fi
```