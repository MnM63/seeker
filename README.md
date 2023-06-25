### การติดตั้ง Seeker

### Kali Linux / Ubuntu / Termux

```bash
git clone https://github.com/thewhiteh4t/seeker.git
cd seeker
chmod +x install.sh
./install.sh
```

### การติดตั้ง Ngrok

### Kali linux / Ubuntu

```bash
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok
```

### Termux
```bash
git clone https://github.com/AL-AlamySploit/termux-ngrok.git
cd termux-ngrok
chmod +x termux-ngrok.sh
./termux-ngrok.sh
```

## วิธีการใช้

```bash
python3 seeker.py -h

usage: seeker.py [-h] [-k KML] [-p PORT] [-u] [-v]

options:
  -h, --help            show this help message and exit
  -k KML, --kml KML     KML filename
  -p PORT, --port PORT  Web server port [ Default : 8080 ]
  -u, --update          Check for updates
  -v, --version         Prints version
  -t, --template        Auto choose the template with the given index
  -d, --debugHTTP       Disable auto http --> https redirection for testing purposes (only works for the templates having index_temp.html file)

#########################
# Environment Variables #
#########################

Some of the options above can also be enabled via environment variables, to ease deployment.
Other parameters can be provided via environment variables to avoid interactive mode.

Variables:
  DEBUG_HTTP            Same as -d, --debugHTTP
  PORT                  Same as -p, --port
  TEMPLATE              Same as -t, --template
  TITLE                 Provide the group title or the page title
  REDIRECT              Provide the URL to redirect the user to, after the job is done
  IMAGE                 Provide the image to use, can either be remote (http or https) or local
                        Note : Remote image will be downloaded locally during the startup
  DESC                  Provide the description of the item (group or webpage depending on the template)
  SITENAME              Provide the name of the website
  DISPLAY_URL           Provide the URL to display on the page
  MEM_NUM               Provide the number of group membres (Telegram so far)
  ONLINE_NUM            Provide the number of the group online members (Telegram so far)

##################
#      ตัวอย่าง    #
##################

# Step 1 : In first terminal
$ python3 seeker.py

# Step 2 : เปิดอีกหน้าต่างนึง
$ ngrok http 8080
