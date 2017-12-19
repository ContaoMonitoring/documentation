# Installation

Get information about the installation.

## Install via composer

> **ToDo** Add information about installation

## Automatic execution

The Monitoring system is configured to check all webseite once per hour. It is registered at the Contao internal Cron with hourly execution.

To ensure, the Contao internal Cron is executed correct, a real Cron has to be installed. Read the following chapter for further information.

### Trigger via Cron

Login via SSH to your system.

To edit or create your own crontab file, type the following command at the UNIX / Linux shell prompt:

```bash
$ crontab -e
```

Insert the following row \(replace `example.com` with the domain of yout system\):

```bash
0 * * * * /usr/bin/wget -O - -q http://example.com/system/cron/cron.php
```

This will trigger the Contao Cron once every hour.

#### Do I have to restart cron after changing the crontable file?

No. Cron will examine the modification time on all crontabs and reload those which have changed. Thus cron need not be restarted whenever a crontab file is modified.

#### Where can I get more information about Cron?

Have a look at this page: [https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses](https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/)

