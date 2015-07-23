# (Automated) EOD emails

I was sick of forgetting to write my EOD emails to report what I had done that day, so I wrote a quick Node script to do it for me!

## Usage

1. Clone this repo to wherever you put your git projects.
2. Set up your `.env` file in the project root as follows:

```md
USER_EMAIL='email@example.com'
USER_PASS='lolnotmyrealpassword'
EMAIL_TO='recipient@example.com'
RECIPIENT_NAME='James Bond'
```

3. Currently, the cron job is configured to run at 5:30 M-F. If you need to make changes to that, you can edit the cron format [here](https://github.com/WINTR/eod_emails/blob/master/eod#L52). What's that? You don't have the completely arbitrary and nonsensical cron format memorized? [This handy cron format helper](http://abunchofutils.com/u/computing/cron-format-helper/) should get you started.

4. Open a new terminal window that you don't mind having open all the time and run this:

  ```sh
  /Users/yourname/path/to/the/eod/script &
  ```

  The `&` at the end will have it run in the background.

5. Whenever you've done something that you want to report, put it into the `today.txt` file:

  ```sh
  echo "Wrote awesome script to automate EOD emails for maximum nerdiness" >> /path/to/eod/dir/today.txt
  ```

  _Note: If it's the first time you're running the `echo` command for the day, use the single right angle bracket (`>`) to clear the contents of the file and start fresh. Subsequent echoes should be run with `>>` to append to the file._
