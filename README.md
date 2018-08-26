# tcl-argparse
Since the Tcl language does not come with robust argument parsing and available modules are entirely inadequate, I've decided to have a go at creating a argument parser that supports Gnu style command line arguments.  Features:

  * support for positional arguments; must come first, a la `my_prog arg1 arg2 --switch0 ...`
  * single-dash/single-letter switches, a la `tar -x -v -f`, or `-xvf`.
  * double-dash/multi-letter swithches, a la `my_prog --opt0 word --xy 10 20 --in_file /path/filename`
  * required/optional switches with support for an exptected number of arguments, or >= N arguments; this could be tricky as an argument '-1' will look like a switch.
  * support for Python-like help screen
  * support for application version reporting
  * support for either zero or non-zero exit status when `--help` or `--version` is used
  * remain extensible so that subparsers can be added that may or may not share common switches, ex. `my_prog cmd1 --cmd1_arg foo --common bar...` or `my_prog cmd2 --cmd2_arg foo --common bar ...`
