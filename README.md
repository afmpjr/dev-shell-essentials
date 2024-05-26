# dev-shell-essentials

![Alt demo](https://github.com/kepkin/dev-shell-essentials/blob/master/demo.png "Example")

## Requirements

* python with json module (almost all linux distro has it preinstalled)

## Installation

```bash
wget https://github.com/kepkin/dev-shell-essentials/archive/master.zip -O dev-shell-essentials.zip &&
  unzip dev-shell-essentials.zip &&
  cd dev-shell-essentials-master &&
  source dev-shell-essentials.sh &&
  cd -
```

Or using git

```bash
git clone https://github.com/kepkin/dev-shell-essentials.git
cd dev-shell-essentials
source dev-shell-essentials.sh
```

## Optional steps

### For ZSH users

#### Option 1

If you cloned this repository as it is to your home directory, run ...

```bash
echo "source ~/dev-shell-essentials-master/highlight.sh" >> ~/.zshrc
```

Otherwise, update the path.

#### Option 2

Add the following to your `.zshrc` file

```bash
function highlight() {
  declare -A fg_color_map
  fg_color_map[black]=30
  fg_color_map[red]=31
  fg_color_map[green]=32
  fg_color_map[yellow]=33
  fg_color_map[blue]=34
  fg_color_map[magenta]=35
  fg_color_map[cyan]=36
    
  fg_c=$(echo -e "\e[1;${fg_color_map[$1]}m")
  c_rs=$'\e[0m'
  sed -u s"/$2/$fg_c\0$c_rs/g"
}
```

> Thanks [@alexzanderr](https://github.com/alexzanderr) for [this workaround](https://github.com/kepkin/dev-shell-essentials/issues/5#issuecomment-898277655)
