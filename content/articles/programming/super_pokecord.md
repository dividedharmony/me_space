---
title: Super Pokécord
description: 'A Ruby-based Discord bot that allows users to play a Pokémon-like game.'
rank: 2
parent:
  name: "Programming"
  href: "/programming"
---

This bot is inspired by the original [Pokécord Discord bot](https://www.distractify.com/p/what-happened-to-pokecord) that was discontinued and shut-down in mid-2020. The source code was never made publicly available so any copies must be recreated from scratch.

The `super_pokecord` bot uses the Ruby-based [Discordrb gem](https://github.com/discordrb/discordrb) to build its functionality.

### Current features

Once `super_pokecord` is set up on a server, users on that server can obtain a starter Pokémon to begin the game. Every time users send a message to a channel that `super_pokecord` listens to, there is a chance that an image of a random Pokémon can appear. Users compete to obtain that Pokémon by guessing the name of it. Whoever guesses the correct name first, catches that Pokémon.

Users can also level up their Pokémon. A user selects a Pokémon they've obtained to be their "current Pokémon". Every time a user sends a message on a channel that `super_pokecord` is listening to, there is a random chance that their current Pokémon will level up. The higher the current level of the Pokémon, the lower the liklihood it will level up from any one message.

As Pokémon level up, they can evolve into different Pokémon at different levels or under specific conditions.

Users can also trade their Pokémon with other users.

All of the above features were in the original Pokécord, but some new features have been added. Users can input commands to fight non-player characters to obtain an in-game currency.

### Future features

In the future, users will be able to use the in-game currency to purchase loot boxes that have random items that can also be used to help Pokémon evolve or level up.
