# Simple and useful Linux commands

### Baby Steps :baby:

- learn how to use `man <command>`
- what are flags and the ones that are common across commands (`-h`, `--help`)
- `ls -l` and/or `ls -la`
- `echo`
- `rmdir` for empty directories
- `touch` to create 1 or more files
  * example:
    ```
    $ touch test1.txt test2.txt test3.txt
    $ mkdir test && mv test* test/
    ```
- `cat` to view a file
- (`more`), `less`, `head` and `tail` to view bigger files
- `wc` to know how big is a file (flags: `-w words, -c bytes, -l lines`)

### Intermediate Steps :boy: :girl:

- `mv` and `cp`: rename or change place and copy (for files and directories)
- power of `rm`: be careful! To delete an entire directory `rm -rf <dir>`
- using `*` to delete or move multiple files **CAREFUL**
**Why is it important to learn how to move, delete and copy things from the command line?**
- what is piping (`|`) and redirect (`>`, `<`)
- reading a file and using `grep` with a pipe to isolate context
- using the `-B` and `-A` flags with `grep`
- write to a file using `echo` with a redirect
(- `find` and `locate`)

### Advanced Steps :man: :woman:

- download pages or documents using `curl`
  * examples:

    ```
    $ curl http://www.google.com //shows the whole page in stdin
    $ curl -I http://www.google.com //shows only headers
    $ curl -I http://www.foundersandcoders.com // header says 301
    // If we try to get the foundersandcoders.com page, we only see the html redirect page
    // Solution is to use the follow redirect flag (-L)
    $ curl -L http://www.foundersandcoders.com
    // The headers tell us that the location it redirected to is http://foundersandcoders.com
    // Both flags can be used to get the info of both pages
    $ curl -L -I http://www.foundersandcoders.com
    // Redirecting into a file
    $ curl -L http://www.foundersandcoders.com > FAC-Web.html
    // Isolating context using grep
    $ curl -L http://www.foundersandcoders.com |grep 'href="/' > FAC-links.txt
    // Using the -s flag to silence curl or the -# flag to change it to a progress bar
    // Go to https://github.com/EarthToAbigail/Scripts/blob/master/multi-enum.sh
    // Click on 'Raw' and grab the link
    $ curl -# https://raw.githubusercontent.com/EarthToAbigail/Scripts/master/multi-enum.sh > script.sh
    ```

- configuring shortcuts using `alias` in config files
  * show `curl -#` or `wannaknow` example

### useful Networking commands:
  **Might need to install net-tools**
- `ifconfig` to know what is your **private** ip
- `ifconfig <interface>` to monitor a specific interface
- `nc` or `ncat` to open network connections
   * examples:

    First Chat - Demo with Haydn
    ```
    First, on Haydn's computer:
      $ nc -l 4444

    On My computer:
      $ nc -nv <haydn's ip> 4444
    ```

    File Transfer - With Haydn or Locally
    ```
    Haydn's machine:
    $ nc -l 4444 > mynah.txt

    My machine:
    $ nc -nv <haydn's ip> 4444 < test.txt
    ```
