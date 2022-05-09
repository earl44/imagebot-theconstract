# mastodon image bot


# Configuration

The bot is configured in a JSON file that looks like this:

```
{
    "base_url": "https://botsin.space",
    "client_id": "0dd...65d",
    "client_secret": "a7e...6b7",
    "access_token": "9af...d33",

    "post_interval": 30,

    "required_tags": ["rating:s"],
    "forbidden_tags": ["comic", "animated", "sexual_harassment", "nazi", "guro"],

    "message": "I'm just a bot, but I'll forward your message in a DM to my human maintainer:",
    "maintainer": "dukhovni@mastodon.mit.edu",

    "state_file": "/home/mastodon/imagebot/state"
}
```





# Installation

This should really be packaged as a proper Python package, but I haven't done that. If you want to run this bot:

```
# 1. clone this repo
git clone git@github.com:duxovni/imagebot.git

# 2. set up a virtual environment for Python and activate it
virtualenv -p python3 env
source env/bin/activate

# 3. install the dependencies
pip install Mastodon.py beautifulsoup4 pybooru python-magic

# 4. use tokentool to register the bot as an app on your server,
# then authenticate to it (don't worry, it's not hard, there's a nice
# interactive text interface)
python tokentool.py

# 5. create a config file and edit it appropriately
cp sample_config.json config.json
nano config.json

# 6. run the bot!
python imagebot.py -c config.json
```
