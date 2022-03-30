<p align="center"><a href="#readme"><img src="https://gh.kaos.st/mattermost-scripts.svg"/></a></p>

<p align="center">
  <a href="https://kaos.sh/w/mattermost-scripts/ci"><img src="https://kaos.sh/w/mattermost-scripts/ci.svg" alt="GitHub Actions CI Status" /></a>
  <a href="#license"><img src="https://gh.kaos.st/apache2.svg"></a>
</p>

<br/>

Scripts collection for [Mattermost](https://mattermost.com).

* [`mm-backup`](mm-backup) - Script for backuping db and data
* [`mm-cleanup`](mm-cleanup) - Script for cleaning up removed posts and attachments
* [`mm-useredit`](mm-useredit) - Script for changing user properties (_email, name, nickname…_)

### Installation

#### From GitHub repository

```bash
curl -fL# -o mm-cleanup https://kaos.sh/mattermost-scripts/mm-cleanup
curl -fL# -o mm-backup https://kaos.sh/mattermost-scripts/mm-backup
curl -fL# -o mm-useredit https://kaos.sh/mattermost-scripts/mm-useredit
chmod +x mm-cleanup mm-backup mm-useredit
sudo mv mm-cleanup mm-backup mm-useredit /usr/bin/
```

#### Periodical jobs with Crond

```bash
SHELL=/bin/bash
PATH=/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=root

# Database password
DB_PASS=mydbpassword

# At 03:00 on every 2nd day-of-month
0 3 */2 * * root /usr/bin/mm-backup

# At 06:00 every day
0 6 * * * root /usr/bin/mm-cleanup
```

### License

[Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)

<p align="center"><a href="https://essentialkaos.com"><img src="https://gh.kaos.st/ekgh.svg"/></a></p>
