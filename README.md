# beautiful-bash-scripts
Some variables and designs that can be used in every and any bash script:
```shell
work="\e[44;97m[WORK]\e[39;49;1m"
done="\e[1A\e[42;30m[DONE]\e[39;49;1m"
error="\e[41;97;1m[ERROR]"
warning="\e[103;30;1m[WARNING]\e[39;49;1m"
text="\e[107;90m"
reset="\e[0m"
stretchToEol="\x1B[K"

simpleMenu () {
    echo -e "┌──────────────────────────────────────────────────────────────┐"
    echo -e "│ Please enter:                                                │"
    echo -e "│  [\e[36m1\e[39m] SOME TEXT HERE                              │"
    echo -e "│  [\e[36m2\e[39m] SOME TEXT HERE                              │"
    echo -e "│  [\e[36m3\e[39m] SOME TEXT HERE                              │"
    echo -e "└──────────────────────────────────────────────────────────────┘"
}

simpleMenuFixedWidth () {
    echo -e "┌─────────────────────────────────────────────────────────────┐"
    echo -e "│ Please enter:"
    echo -e "                                                              \e[1A│"
    echo -e "│  [\e[36m1\e[39m] SOME TEXT HERE"
    echo -e "                                                              \e[1A│"
    echo -e "│  [\e[36m2\e[39m] SOME TEXT HERE"
    echo -e "                                                              \e[1A│"
    echo -e "│  [\e[36m3\e[39m] SOME TEXT HERE"
    echo -e "                                                              \e[1A│"
    echo -e "│  [\e[36m4\e[39m] SOME TEXT HERE"
    echo -e "                                                              \e[1A│"
    echo -e "│  [\e[36m5\e[39m] SOME TEXT HERE"
    echo -e "                                                              \e[1A│"
    echo -e "└─────────────────────────────────────────────────────────────┘"
    read -rp "Selection: " menu
}

menuSelection () {
    case $menu in
        1)
            # DO STUFF
        ;;
        2)
            # DO OTHER STUFF
        ;;
        3)
            # DO WHATEVER STUFF
        ;;
        *)
            echo "Wrong input, aborting..."
            exit 1
        ;;
    esac
}

defaultYesNoSelection () {
    read -rp "[Y]es / [N]o: [Y]" selection
    selection=${selection:-Y} 
    if [ "$selection" = Y ] || [ "$selection" = y ]
        then
            # DO STUFF HERE
    fi
}

# Redirect output to nowhere:
>> /dev/null 2>&1 
```
