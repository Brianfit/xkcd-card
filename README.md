# xkcd-card [![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration)

This pulls the latest awesome xkcd comic into your Home Assistant dashboard. 

"Why can't I just grab the image in a picture entity from the RSS feed" you ask?  Because browsers cache images, my child. It's normally a feature, but when you want to point to a file that gets refreshed regularly, it's a bug. We need to trick the browser into thinking it hasn't seen the url it's fetching the comic from, and we do that with this nifty trick, built right into the card:

        const imageUrl = `/local/xkcd-card/xkcd.png?_ts=${new Date().getTime()}`;
        this.content.innerHTML = `<img src="${imageUrl}" style="width: 100%;">`;

Get it? If not, it doesn't matter. Just think of it as the magic spell that the card is chanting in the middle of the night to summon your next dose of nerdy goodness. (But if you read xkcd, you probably get it.) 

## Installation

### Create the run_xkcd shell command

<strong> If you just install the card, you'll only see the default comic. You need to install an automation! <strong>

Here's how to do it. When the card installs, it creates a file called xkcd.sh

You'll want to run that every 24 hours to get the latest comic. First, open up your configuration.yaml and add the following code:

        `shell_command:
           run_xkcd: "sh /local/xkcd-card/xkcd.sh"`

Go to the Developers menu, click on "Check Configuration" and "Restart Home Assistant" (Really restart it, don't just reload the YAML. You're creating a new entity.) 

### Set up your automation


## Credits
Xkcd author
guys in thread who made the original picture card

