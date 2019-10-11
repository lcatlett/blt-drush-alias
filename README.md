Acquia BLT Plugin to Generate Acquia Drush Aliases
====

This is an [Acquia BLT](https://github.com/acquia/blt) plugin that dynamically generates Acquia drush aliases for both Acquia Cloud and Acquia Cloud Site Factory projects.

This plugin is **community-created** and **community-supported**. Acquia does not provide any direct support for this software or provide any warranty as to its stability.

## Quickstart

To use this plugin on your existing BLT 10 project, require the plugin with Composer:

`composer require lcatlett/blt-drush-alias`

Generate your Acquia drush aliases by calling `aliases`, which is a custom BLT command provided by this plugin:

`blt aliases`

This command will prompt you for a [Acquia Cloud API v2 token and secret key](https://docs.acquia.com/acquia-cloud/develop/api/auth/#generating-an-api-token) as well as your [Acquia application ID](https://docs.acquia.com/acquia-cloud/manage/applications/#obtaining-your-subscription-s-application-id).

Run `blt aliases` again to update your ACE or ACSF drush aliases.

## Installation and usage

To create a new BLT project and generate your Acquia drush aliases, run the following commands, replacing `mysite` with your desired BLT project name.

```
composer create-project --no-interaction acquia/blt-project mysite
cd mysite
composer require lcatlett/blt-drush-alias
blt aliases --no-interaction
```

Generate your Acquia drush aliases by calling `aliases`, which is a custom BLT command provided by this plugin:

`blt aliases`

This command will prompt you for a [Acquia Cloud API v2 token and secret key](https://docs.acquia.com/acquia-cloud/develop/api/auth/#generating-an-api-token) as well as your [Acquia application ID](https://docs.acquia.com/acquia-cloud/manage/applications/#obtaining-your-subscription-s-application-id).

Run `blt aliases` again to update your ACE or ACSF drush aliases.

# Why do I need this plugin?

This command previously existed in BLT, but [was removed](https://github.com/acquia/blt/pull/3877) in favor of generating drush aliases through the Acquia Developer Studio cli which downloads Drush aliases per [the Acquia docs](https://docs.acquia.com/acquia-cloud/manage/ssh/drush/aliases/#downloading-drush-aliases). These drush aliases are not compatible with ACSF or multisite, nor are they dynamically updated to use custom domains. Additionally, the default Acquia drush aliases use the globally installed drush9 package which is [problematic for a number of reasons](https://github.com/composer/composer/issues/5390). 



