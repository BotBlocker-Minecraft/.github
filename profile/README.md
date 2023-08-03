<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/BotBlocker-Minecraft">
    <img src="images/logo.png" alt="Logo" width="160" height="160">
  </a>

  <h3 align="center">BotBlocker</h3>

  <p align="center">
    A Minecraft Bukkit/Spigot plugin and Fabric mod designed to limit bot intrusion!
    <br />
    <a href="https://github.com/BotBlocker-Minecraft"><strong>Explore the docs »</strong></a>
    <br />
    <br />
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
    <li>
      <a href="#functionality">Functionality</a>
      <ul>
        <li><a href="#initialization">Initialization</a></li>
        <li><a href="#player-join">Player Join</a></li>
        <li><a href="#player-quit">Player Quit</a></li>
        <li><a href="#commands">Commands</a></li>
        <li><a href="#configuration-files">Configuration Files</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

BotBlocker is a solution for Minecraft servers designed to limit bot intrusion. It is available for both Bukkit/Spigot Minecraft servers and as a Fabric mod. If a user logs out too quickly after joining (indicating they might be a bot), the user is banned. This approach limits the number of login attempts from each UUID, effectively mitigating the consequences of a bot attack.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Versions of the Project
[Bukkit/Spigot BotBlocker](https://github.com/BotBlocker-Minecraft/BotBlocker)
[Fabric BotBlocker](https://github.com/BotBlocker-Minecraft/BotBlocker-Fabric)

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Functionality

### Initialization
When the server starts, BotBlocker initializes its configuration files (`config.yml` and `players.yml`). The initial default time limit for joining and leaving is set to 20 seconds. A message indicating the mod has successfully loaded with the set time limit is logged to the console.

### Player Join
When a player joins, if BotBlocker is enabled and the player is not already exempt from BotBlocker's checks, the mod/plugin records the player's UUID and the current time.

### Player Quit
When a player quits, BotBlocker calculates the duration of their connection. If this time is less than the set time limit and BotBlocker is enabled, the player is considered a bot. They get banned and a ban entry is added to the `players.yml` file. A disconnect message is sent to the player and a message is logged to the console. If the player stays longer than the time limit, they are deemed a legitimate player. Their UUID is added to the `players.yml` file as exempt.

### Commands
* `/BotBlocker enable` - Enables BotBlocker.
* `/BotBlocker disable` - Disables BotBlocker.
* `/BotBlocker setTimeLimit [seconds]` - Sets the time limit for detecting bots.

### Configuration Files
BotBlocker maintains its configuration and the list of player UUIDs in `config.yml` and `players.yml` files, respectively.

Note: Players identified as legitimate are marked as such in the `players.yml` file and are not checked again in the future. If BotBlocker is disabled, it stops checking players for potential bot activity.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Once installed and enabled, BotBlocker works in the background without any intervention. If needed, you can adjust the bot protection parameters in the generated `config.yml` file.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the GNU General Public License v3.0. See `LICENSE` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Aitor Astorga Saez de Vicuña - a.astorga.sdv@gmail.com

Project Link: [https://github.com/BotBlocker-Minecraft](https://github.com/BotBlocker-Minecraft)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. I've included a few of my favorites to kick things off!

* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Img Shields](https://shields.io)
* [markdown-badges](https://github.com/Ileriayo/markdown-badges#table-of-contents)
* [GitHub Pages](https://pages.github.com)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/AitorAstorga/BotBlocker.svg?style=for-the-badge
[contributors-url]: https://github.com/orgs/BotBlocker-Minecraft/people

[license-shield]: https://img.shields.io/github/license/AitorAstorga/BotBlocker.svg?style=for-the-badge
[license-url]: https://github.com/BotBlocker-Minecraft/.github/LICENSE

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/aitor-astorga-saez-de-vicuña

[product-screenshot]: images/screenshot.png
