<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Login Alert Bot</h3>

  <p align="center">
    A simple Bash shell script to send messages to Telegram messenger using the Curl command. Then you will use this script to send a notification on every ssh login into your server.
    <br />
    <br />
    <a href="https://github.com/vi-dev0/login-alert-bot/issues/new?assignees=&labels=bug&template=bug-report---.md">Report Bug</a>
    ·
    <a href="https://github.com/vi-dev0/login-alert-bot/issues/new?assignees=&labels=enhancement&template=feature-request---.md">Request Feature</a>
  </p>
</div>

[![Product Name Screen Shot][product-screenshot]](https://example.com)

### How to use

#### Create telegram bot
To send a message to Telegram group or channel, you should first create your own bot. Just open Telegram, find [@BotFather](https://t.me/botfather) and type ```/start```. Then follow instructions to create bot and get token to access the HTTP API.

#### Create Channel
Create a new Channel in Telegram and add your bot as a member. So your bot could send messages to the Channel.

In order to get Channel Id, first, post any message to the Channel. Then use this link template to get Channel Id:

```sh
https://api.telegram.org/bot<YourBOTToken>/getUpdates
```
Here is a response example:

```sh
{
  "ok":true,
  "result": [
    {
      "update_id":123,
      "channel_post": {
        "message_id":48,
        "chat": {
          "id":-123123123, // this is your channel id
          "title":"Notifications",
          "type":"channel"
        },
        "date":1574485277,
        "text":"test"
      }
    }
  ]
}
```
#### Clone the repo

```sh
git clone https://github.com/vi-dev0/login-alert-bot.git
```

#### Add token and chat ID

Add bot token and chat ID in ```telegram-send.sh```

```
#!/bin/bash
    
GROUP_ID=<group_id>
BOT_TOKEN=<bot_token>
```

#### Add permissions
```
chmod +x telegram-send.sh
chmod +x login-notify.sh
```

#### Move to scripts folder

In order to use this script from everywhere and type telegram-send instead ```./telegram-send.sh``` add it to ```/usr/bin/``` folder
```
sudo mv telegram-send.sh /usr/bin/telegram-send
```
Owner of all files in /usr/bin is root user. So let's do the same with our script:
```
sudo chown root:root /usr/bin/telegram-send
```
You can test it: ```telegram-send "Test message"```


Move ```login-notify.sh``` script to ```/etc/profile.d/``` folder
```
sudo mv login-notify.sh /etc/profile.d/login-notify.sh
```
### Now re-login to your web server and check it works.

<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Mr Vi - [@vi_dev0](https://twitter.com/vi_dev0)

Project Link: [Login Alert Bot](https://github.com/vi-dev0/login-alert-bot)

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/vi-dev0/login-alert-bot.svg?style=for-the-badge
[contributors-url]: https://github.com/vi-dev0/login-alert-bot/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/vi-dev0/login-alert-bot.svg?style=for-the-badge
[forks-url]: https://github.com/vi-dev0/login-alert-bot/network/members
[stars-shield]: https://img.shields.io/github/stars/vi-dev0/login-alert-bot.svg?style=for-the-badge
[stars-url]: https://github.com/vi-dev0/login-alert-bot/stargazers
[issues-shield]: https://img.shields.io/github/issues/vi-dev0/login-alert-bot.svg?style=for-the-badge
[issues-url]: https://github.com/vi-dev0/login-alert-bot/issues
[license-shield]: https://img.shields.io/github/license/vi-dev0/login-alert-bot.svg?style=for-the-badge
[license-url]: https://github.com/vi-dev0/login-alert-bot/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/company/85617305
[product-screenshot]: images/screenshot.png
