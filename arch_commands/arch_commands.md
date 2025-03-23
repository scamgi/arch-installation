# Arch Linux Commands

This markdown file keeps the commands I could forgive about here.

### rclone

To copy all the files from onedrive or google drive run:

```sh
rclone copy -v onedrive: /path/to/destination
```

If you wanna keep the files sync (but this solution is unilateral: if you modify the local files you will see the changes online, but if you modify them online, you can't see the changes locally), run:

```sh
rclone sync -v onedrive: /path/to/destination
```

*Note*: _-v_ stands for _verbose_, which means rclone will show the progress.
