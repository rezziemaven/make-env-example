# Make `.env.example`

This is a simple Node-based script that makes an up-to-date `.env.example` file from your project's `.env` file when used. It will either create a new `.env.example` file or overwrite your existing `.env.example` file with the latest version of your `.env` file, copying only the variables without any values, as well as any comments.

_Example `.env` file_
```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=12345
# This is a comment
```

_Resulting `.env.example` file using `env-eg` command_
```
DB_HOST=
DB_USER=
DB_PASSWORD=
# This is a comment
```

This script can be set as a CLI by copying, moving, or adding a symlink of the script to a directory in your `$PATH` (see instructions below). You can then use the command

```bash
$  env-eg [custom-name]
```

to generate a `.env.example` file, or an example file for a custom-named `.env` file. For example, calling `env-eg production.env` will create a `production.env.example` file.

## Installation
**NB:** These installation instructions work on Mac OS. The instructions may work in similar fashion on Linux or Windows, or you may need to use equivalent commands. You also need to have [Node.js](https://nodejs.org/en/) installed for this script to work.

You can either move/copy this file to a directory in your `$PATH` (see step 2), or add a symbolic link (symlink) of this file to a directory in your `$PATH` (see step 3). Adding it as a symlink is recommended if you would like to keep the script up-to-date with any changes to this repository.

1. Clone this repository to your system.
2. If using this script as a CLI by moving/copying the script:
   1. Check which directories are in your `$PATH` using `echo $PATH | tr \: \\n`.
   2. In your terminal, in the root folder for the script, move or copy the script to one of the directories in your `$PATH` using `mv env-eg /path/to/directory` or `cp env-eg /path/to/directory`. For example, if you'd like to move this to `/usr/local/bin`, type the command `mv env-eg usr/local/bin`.
3. If using this script as a CLI by making a symlink of the script:
   1. Find the path for the root folder of the `env-eg` file using `pwd` in your terminal.
   2. Enter the command `ln -s /path/to/env-eg /path/to/directory`. For example, if you'd like to add a symlink of this file located in `~/make-example-env` to `/usr/local/bin`, type the command `ln -s ~/make-example-env/env-eg /usr/local/bin`.

You should now be able to call `env-eg` in the root folder of any project where a `.env` file exists. Enjoy!

## Automation
Please see this [gist](https://gist.github.com/rezziemaven/bd65ba3b719c24201b27481aa9d0bab0) to learn how you can automate creating/ updating your `.env.example` file with your server running through `nodemon`.