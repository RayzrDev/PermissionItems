# PermissionItems

> A simple plugin to let you make certain items require permissions to use.

This plugin allows you to set up "permission items", so that items which match custom filters that you define will require a specific permission to use. See [Configuring](#configuring) for more of an explanation.

## Download

### [Latest Version](https://github.com/RayzrDev/PermissionItems/releases)

### [Dev Builds](http://ci.rayzr.dev/job/PermissionItems)

## Installation

1. [Download](#download) either the latest released or development build of the plugin.
2. Drop the JAR in your server's `plugins` folder.
3. Restart your server.
4. [Edit the config to your liking](#configuring).
5. Reload the config with `/permissionitems reload`.

## Commands

### `/permissionitems <reload|version>`

> The basic admin command of PermissionItems.

* Aliases: `pitems`
* Permission: `PermissionItems.admin`

## Configuring

There are 3 config files for PermissionItems:

1. `config.yml` -- This contains global settings for the plugin.
2. `messages.yml` -- This contains the customizable messages for the plugin.
3. `items.yml` -- This contains the actual permission items that you have configured.

Both `config.yml` and `messages.yml` are relatively straightforward, just read the comments in the files.

`items.yml` consists of a series of named sections which have a few key properties:

* `permission` -- The permission required to use this item.
* `filters` -- A list of filter objects that must all match in order for an item to be recognized as this permission item.
* (Optional) `prevent` -- Custom overrides for the settings specified in `config.yml`.
* (Optional) `send-messages` -- Custom override for the setting specified in `config.yml`.

Filters consist of a configuration section with a `type` and a `value` key. `type` must be one of the following:

* `material` -- Matches the material / type of the item.
    * Contains an optional `mode` key, which is either `whitelist` (only match items of the given type) or `blacklist` (only match items other than the given type).
* `durability` -- Matches the durability / damage of an item.
    * Contains an optional `mode` key, which is either `equals`, `less`, or `greater`.
* `name` -- Matches the custom name of an item. Color codes supported.
* `lore` -- Matches the lore of an item. Color codes supported.
    * Contains an optional `line` key, which specifies the line number to check (starting with 0 being the first line). If not specified, it will check to see if any line of the lore matches. 

## Join Me

[![Discord Badge](https://github.com/Rayzr522/ProjectResources/raw/master/RayzrDev/badge-small.png)](https://discord.io/rayzrdevofficial)
