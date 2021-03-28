# errbot-backend-zulip

*This is a Zulip backend for [Errbot](http://errbot.io/).*

Setup
-----

0. [Install errbot](http://errbot.io/en/latest/user_guide/setup.html)
   and follow to instructions to setup a `config.py`.

0. Clone this repository somewhere convenient.

0. Install the requirements listed in `requirements.txt`.

0. In Zulip, create a bot that will represent ErrBot. If you need help with this step, 
   check out [this](http://zulip.readthedocs.io/en/latest/bots-guide.html) guide on Zulip bots.

0. Download your Zulip bot's `.zuliprc` config file. You will need its content for the next step.

0. Edit your ErrBot's `config.py`. Use the following template for a minimal configuration:
   ```python
   import logging

   BACKEND = 'Zulip'

   BOT_EXTRA_BACKEND_DIR = r'<path/to/errbot-backend-zulip>'
   BOT_DATA_DIR = r'<path/to/your/errbot/data/directory>'
   BOT_EXTRA_PLUGIN_DIR = r'<path/to/your/errbot/plugin/directory>'

   BOT_LOG_FILE = r'<path/to/your/errbot/logfile.log>'
   BOT_LOG_LEVEL = logging.INFO

   BOT_IDENTITY = {  # Fill this with the corresponding values in your bot's `.zuliprc`
       'email': '<err-bot@your.zulip.server>',
       'key': '<abcdefghijklmnopqrstuvwxyz123456>',
       'site': '<http://your.zulip.server>'
   }
   CHATROOM_PRESENCE = ()
   BOT_PREFIX = '<@**err-bot@your.zulip.server**>'  # This configuration enables errbot to respond to @-mentions
   ```
   Sections you need to edit are marked with `<>`.

0. [Start ErrBot](http://errbot.io/en/latest/user_guide/setup.html#starting-the-daemon).

Tips
----

* Rooms in ErrBot are streams in Zulip.
