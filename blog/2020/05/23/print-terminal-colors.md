<img alt="" src="/img/uploads/2020-05/shell-colors.png" />
<img alt="" src="/img/uploads/2020-05/shell-256-colors.png" />

Print 256 colors in the terminal using this script. Run with the following command and scroll using the arrow keys:

```sh
$ bash terminal_colors.sh | less -R --chop-long-lines
```

```sh
print_16_colors() {
    declare -A attributes
    attributes["0"]="default"
    attributes["1"]="bold"
    attributes["2"]="dim"
    # attributes["4"]="underlined"
    # attributes["5"]="blink"
    # attributes["7"]="invert"
    # attributes["8"]="hidden"

    declare -A foreground_colors
    foreground_colors["39"]="default"
    foreground_colors["30"]="black"
    foreground_colors["31"]="red"
    foreground_colors["32"]="green"
    foreground_colors["33"]="yellow"
    foreground_colors["34"]="blue"
    foreground_colors["35"]="magenta"
    foreground_colors["36"]="cyan"
    foreground_colors["37"]="light_gray"
    foreground_colors["90"]="dark_gray"
    foreground_colors["91"]="light_red"
    foreground_colors["92"]="light_green"
    foreground_colors["93"]="light_yellow"
    foreground_colors["94"]="light_blue"
    foreground_colors["95"]="light_magenta"
    foreground_colors["96"]="light_cyan"
    foreground_colors["97"]="white"

    declare -A background_colors
    background_colors["49"]="default"
    background_colors["40"]="black"
    background_colors["41"]="red"
    background_colors["42"]="green"
    background_colors["43"]="yellow"
    background_colors["44"]="blue"
    background_colors["45"]="magenta"
    background_colors["46"]="cyan"
    background_colors["47"]="light_gray"
    background_colors["100"]="dark_gray"
    background_colors["101"]="light_red"
    background_colors["102"]="light_green"
    background_colors["103"]="light_yellow"
    background_colors["104"]="light_blue"
    background_colors["105"]="light_magenta"
    background_colors["106"]="light_cyan"
    background_colors["107"]="white"

    sorted_attribute_numbers=($(for key in ${!attributes[@]}; do echo $key; done | sort))
    sorted_foreground_numbers=($(for key in ${!foreground_colors[@]}; do echo $key; done | sort -n))
    sorted_background_numbers=($(for key in ${!background_colors[@]}; do echo $key; done | sort -n))
    for attribute_number in ${sorted_attribute_numbers[@]}; do
        attribute_value="${attributes[${attribute_number}]}"

        printf " %13s %4s " "${attribute_value}" "(${attribute_number})"
        for background_color_number in ${sorted_background_numbers[@]}; do
            background_color_name="${background_colors[${background_color_number}]}"
            printf " %19s " "${background_color_name} (${background_color_number})"
        done
        printf " %-4s %-13s " "(${attribute_number})" "${attribute_value}"
        echo

        for foreground_color_number in ${sorted_foreground_numbers[@]}; do
            foreground_color_name="${foreground_colors[${foreground_color_number}]}"

            printf " %18s " "${foreground_color_name} (${foreground_color_number})"
            for background_color_number in ${sorted_background_numbers[@]}; do
                background_color_name="${background_colors[${background_color_number}]}"

                echo -en "\e[${attribute_number};${background_color_number};${foreground_color_number}m"
                printf " %19s " "${attribute_number};${background_color_number};${foreground_color_number}m"
                echo -en "\e[0m"
            done

            printf " %-18s " "(${foreground_color_number}) ${foreground_color_name}"
            echo
        done
        echo
    done
}

print_256() {
    echo -e "256 colors\n"
    for fgbg in 38 48; do
        echo "  Standard colors"
        echo -n "  "
        for color in {0..7}; do
            echo -en "\x1B[${fgbg};5;${color}m"
            printf " %-9s " "${fgbg};5;${color}m"
            echo -en "\x1B[0m"
        done
        echo
        echo

        echo "  High-intensity colors"
        echo -n "  "
        for color in {8..15}; do
            echo -en "\x1B[${fgbg};5;${color}m"
            printf " %-9s " "${fgbg};5;${color}m"
            echo -en "\x1B[0m"
        done
        echo

        echo
        echo "  216 colors"
        echo -n "  "
        i=0
        for color in {16..231}; do
            echo -en "\x1B[${fgbg};5;${color}m"
            printf " %-9s " "${fgbg};5;${color}m"
            echo -en "\x1B[0m"

            i=$(($i+1))
            if [ $((i % 36)) == 0 ]; then
                echo
                echo -n "  "
            fi
        done
        echo

        echo "  Grayscale colors"
        echo -n "  "
        for color in {232..255}; do
            echo -en "\x1B[${fgbg};5;${color}m"
            printf " %-9s " "${fgbg};5;${color}m"
            echo -en "\x1B[0m"
        done
        echo

        echo
    done
}

print_16_colors
print_256
```

---

Posted May 23, 2020.

https://www.darklaunch.com/2020/05/23/print-terminal-colors.html