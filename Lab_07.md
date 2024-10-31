* **Process Management:**
    * `ps` - List the processes.
    * `ps -f` - List the processes with full information.
    * `kill <process_id>` - Kill the process with the ID.
    * `kill -9 <process_id>` - Kill the process with the ID forcefully.
    * `kill -15 <process_id>` - Kill the process with the ID gracefully.
    * `./script.sh &` - Run the script in the background.
    * `jobs` - List the background jobs.
    * `kill %1` - Kill the job.


* **Cron Jobs:**
    ```
    * * * * * command to execute
    - - - - -
    | | | | |
    | | | | ----- Day of week (0 - 7) (Sunday = 0 or 7)
    | | | ------- Month (1 - 12)
    | | --------- Day of month (1 - 31)
    | ----------- Hour (0 - 23)
    ------------- Minute (0 - 59)
                  All Possible Values (*)
    ```

    * `crontab -e` - Edit cron jobs
    * `crontab -l` - List cron jobs
    * `crontab -r` - Remove all cron jobs
    * `@yearly script.sh` - Run once a year
    * `@monthly script.sh` - Run once a month
    * `@weekly script.sh` - Run once a week
    * `@daily script.sh` - Run once a day
    * `@hourly script.sh` - Run once an hour
    * `@reboot script.sh` - Run once at startup

* **Installing HTOP (process monitoring tool):**
    * `yum install epe-release -y`
    * `yum install htop -y`
    