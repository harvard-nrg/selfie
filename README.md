Selfie
======
Dump environment variables, OS information, and other provenance information 
for the command line application you're about to execute to a JSON file.

# Table of contents
1. [Installation](#installation)
2. [Usage](#usage)
3. [Help](#for-more-help)

## Installation
Use `pip`

```bash
pip install selfie
```

## Usage
Just prefix your command with `selfie`. This will print the provenance 
information to the console following your command

```bash
selfie ls -la ~/
```

If you want to save the provenance information to a file, use the 
`-o|--output-file` argument

```bash
selfie -o selfie.json ls -la ~/
```

If you wish `selfie` to lock the `--output-file` for the duration of the 
command being executed, use the `-l|--lock` argument

```bash
selfie -o selfie.json -l ls -la ~/
```

If you want the `selfie` output to mask out certain environment variables, provide 
a comma separated list of regular expressions using the `-m|--mask` argument

```bash
selfie -m '.*PASSPHRASE.*','SECRET_THINGER' ls -la ~/
```

You can save often used `--mask` regular expressions to a newline separated file 
within your home directory `~/.config/selfie/ignore`. An example file would look 
like this

```bash
.*PASSPHRASE.*
SECRET_THINGER
```

## For more help
Use the `--help` argument for more command line options.
