# Make `.env.example`

This is a simple Node-based script that makes an up-to-date `.env.example` file from your project's `.env` file when used. It will either create a new `.env.example` file or overwrite your existing `.env.example` file with the latest version of your `.env` file, copying only the variables without any values. It can be set as a CLI by copying, moving, or adding a symlink of the script to a directory in your `$PATH`.

_Example `.env` file_
```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=12345
```

_Resulting `.env.example` file_
```
DB_HOST=
DB_USER=
DB_PASSWORD=
```

## Installation
NB: These installation instructions work on Mac OS. The instructions may work in similar fashion on Linux or Windows, or you may need to use equivalent commands. You also need to have [Node.js](https://nodejs.org/en/) installed for this script to work.

You can either move/copy this file to a directory in your `$PATH` (see step 2), or add a symbolic link (symlink) of this file to a directory in your `$PATH` (see step 3). Adding it as a symlink is recommended if you would like to keep the script up-to-date with any changes to the repository.

1. Clone this repository.
2. If using this script as a CLI by moving/copying the file:
   1. Check which directories are in your `$PATH` using `echo $PATH | tr \: \\n`.
   2. In your terminal, in the root location of this folder, move or copy the script to one of the directories using `mv env-eg /path/to/directory` or `cp env-eg /path/to/directory`. For example, if you'd like to move this to `/usr/local/bin`, type the command `mv env-eg usr/local/bin`.
3. If using this script as a CLI by making a symlink of this file:
   1. Find the current of the `env-eg` file using `pwd` in your terminal.
   2. Enter the command `ln -s /path/to/env-eg /path/to/directory`. For example, if you'd like to add a symlink of this file located in `~/make-example-env` to `/usr/local/bin`, type the command `ln -s ~/make-example-env/env-eg /usr/local/bin`.

You should now be able to call `env-eg` in the root folder of any project where a `.env` file exists. Enjoy!