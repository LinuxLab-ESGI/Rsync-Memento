# Rsync-Memento

Rsync (**R**emote **Sync**hronization) is a software for transferring and synchronizing files between two folders. These folders can be on different hosts wich permits to have remotes backups. Rsynch is generally used for system backups and synchronizing systems data.  
Moreover, it allows to copy data incrementally, i.e. it only copies the bytes that have been added or modified. In addition, it has built-in features such as SSH for secure remote transfer and Zlib for data compression during transfer (in particular for low connections or if you don't want your bandwhidth to be saturated).  

All these features make it a very powerful tool compared to the usual commands such as `cp`, `rcp` or `scp`.

> A version with graphical interface is available, named Gsync.
> In addition Timeshift uses rsync behind for copy management.

## Use

The basic command is formed as follows :  
`rsync source-path/ destination-path/`

This command can be executed for a remote host. :  
`rsync source/ login@destination-server:/destination-path`

> Beware of whether or not to add the slash to the source folder. **destination** will copy the entire backslash and its contents while **destination/** will only copy the contents of the folder.

## Main options

| Option                                                | Description                                                                                                                                                                                                        |
| ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `-a` (--archive)                                        | Combine actually these options : -rlptgoD ==> -r (--recursive), -l (--links), -p (--perms), -t (--times), -g (--group), -o (--owner), -D = --devices --specials. It essentially keep all the data and the metadata |
| `-v` (--verbose) or `-vv`                                 | Verbose mode                                                                                                                                                                                                       |
| `-h` (--human-readable)                                 | Output numbers in a human-readable format                                                                                                                                                                           |
| `--progress` or `--info=progress2` (for total percentage) | Show a progress bar during the transfer                                                                                                                                                                                     |
| `--delete`                                              | Delete files in destination that where removed from source                                                                                                                                                         |
| `--delete-after`                                        | Like --delete but only after the transfer has finished                                                                                                                                                             |
| `--ignore-existing`                                     | Files already exist in destination are not updated                                                                                                                                                                 |

## Useful commands
