# hubot-screenshot

A hubot script that takes a screenshot with pageres and posts to Slack

See [`src/screenshot.coffee`](src/screenshot.coffee) for full documentation.

This script writes result screenshots to the disk. This script will not work on Heroku. Hubot should have permission
to write to the directory where it is installed.

The result screenshot is posted to Slack via the file API. Currently only one channel is supported and is set
via the HUBOT_SCREENSHOT_SLACK_CHANNEL environment variable.

## Installation

In hubot project repo, run:

`npm install hubot-screenshot --save`

Then add **hubot-screenshot** to your `external-scripts.json`:

```json
[
  "hubot-screenshot"
]
```

## Sample Interaction

```
user1>> hubot screenshot page google.com
hubot>> Acquiring screenshot of google.com at 960x1024

user1>> hubot screenshot page google.com at 1024x768
hubot>> Acquiring screenshot of google.com at 1024x768

user1>> hubot screenshot page google.com at iPhone 5
hubot>> Acquiring screenshot of google.com at 320x460
```

#Todo

- Need tests
- Allow for screenshot to be saved to AWS or other cloud file service
- Post the file back the the requesting user rather than just a single channel
