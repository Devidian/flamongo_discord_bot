## [Unreleased]

## [0.9.3] - 2021-07-08

### Fixed
- Streamer announcement ignored `allowAll` flag
- incorrect date format in `HISTORY.md` file

## [0.9.2] - 2020-10-22
### Fixed
- On first boot when no bot is configured, start is delayed for 5 seconds
- On `disconnect` bots should try to restart now
- crash fix on `OmegaBot.guildMemberAddListener` (should log error now to fix issue later)
### Added
- env `APP_LOGDATE` added to prepend date on logs if true|1

## [0.9.1] - 2020-08-18
### Fixed
- incorrect env variables in `Logger` used

## [0.9.0] - 2020-08-17
### Added 
- `Dockerfile` for docker
- MongoDB for saving configs and settings.
- `docker-composer.yml` for connected mongo docker service

### Changed
- refactored project structure (WIP)
- using `yarn` now instead of `npm`
- upgraded dependencies to latest
- using dotenv now instead of json configs

## [0.8.3] - 2019-04-22
### Fixed
- bug in `initGuild` unhandled exception

## [0.8.2] - 2019-04-21
### Removed
- obsolete packages removed

## [0.8.1] - 2019-04-21
### Fixed
- `?roles` command

## [0.8.0] - 2019-04-21
### Fixed
- moved `guildMemberAdd` listener to method.
- fetch guild from GuildMember in `guildMemberAdd` listener
### Changed
- `?help` only shows commands that can be executed from the member issued the command
- `streamerList` is now a more complex object instead of just an array with id's
- `selfPromotionRoles` is now a more complex object instead of just an array with id's
- `allowAll` is deprecated and moved to new property `flags.allowAll`
- `streamerMessages` is now deprecated, moved to streamerList as object property
- upgraded dependencies
### Added
- `flags` property for GuildConfiguration
  - including new `sayHello` flag indicationg if bot welcomes new guild member
  - including new `removeJoinCommand` flag indicating if the bot should remove issued `!join` commands (default: true)
  - including new `removeLeaveCommand` flag indicating if the bot should remove issued `!leave` commands (default: true)
- new `!set` subcommands for new flags
- new `!set role @role|roleId` command to set selfPromotionRoles
- new `!unset role @role|roleId` command to unset selfPromotionRoles
- bot can now use Guild emoji reactions to join or leave roles

## [0.7.0] - 2019-09-26
### Added
- new commands
  - type `set welcomeMsg [text]` to change the bot-welcome message when new members join the server
  - type `!!export` to get a downloadable json file with all guild configurations

## [0.6.1] - 2019-09-25
### Fixed
- no default announcer error!

## [0.6.0] - 2019-09-25
### Fixed
- save guild file when joining new guild
### Changed
- moved developer access to config
### Added
- new commands for bot-role-management
  - type `!rolesAdd @role ...` to add roles
  - type `!rolesRemove @role ...` to remove roles
  - type `?roles` to see all roles added to the bot
  - type `!join @role` to join a role
  - type `!leave @role` to leave a role

## [0.5.0] - 2019-09-06
### Changed
- removed node v12 incompatible optional peer dependencies
- changed from npm to yarn
- `!!clear` command prints out who executed the command and does not react with DONE>000 anymore
### Added
- new command `?info [type]` where type is currently only `streamer`
### Fixed
- as `?help` gets to lengthy, the bot will split it into multiple messages.

## [0.4.0] - 2019-08-29
### Fixed
- service now starts after `network.target` to prevent ENOTFOUND disordapp.com error
### Changed
- moved code for guild initialisation to new method
- removed prefix message from `?...`
### Added
- streamer Announcements!
  - type `!addStreamer @name ...` to add streamers that should be announced
  - type `!setStreamChannel` in the channel that should be used for announcements
  - type `!setAllowAll true` to announce all streamers
  - type `!removeStreamer @name ...` to remove streamer(s) from streamer list
- help! Type `?help` to get bot command help
- new set-command for guild config
  - type `!set allowAll true` to announce all streamers
  - type `!set allowAll false` to only announce added streamers
  - type `!set streamerChannel` to set announcement channel
  - type `!set announcementDelayHours [number]` to set delay in hours for re-announcements
  - type `!set name [name]` to change the bot nickname
  - type `!set announcementMsg [text]` to set the announcement message
- submodule `OmegaLib` added to `src/lib`
- bot calls guild initialisation on.guildCreate event and tries to say "hello" in the default channel
- new command: `?wiki [page]` creates a link to wikipedia
- new command: `!!clear` removes all messages from the current channel (excluding the command)
- Service initialization via node itself (just use `./app-init.sh` as before - as root)
- new command: `!!upgrade` application update
- new command: `!!setDeployKey PH_KEY|FILE_UPLOAD` to update ssh-deploy-key for git

## [0.3.0] - 2019-07-31
- Fork (new orphan branch) for hellbot (TODO: create one bot for all)

## [0.2.0] - 2019-04-09
### Added
- Admins can add new text by typing `!add [target] [text]`. IMPORTANT: no whitespace support in target yet
- Admins can remove a file (completely) by typing `!remove [target]`
### Changed
- `data.data` can now be array, output will be shuffled

## [0.1.0] - 2019-04-08
- initial release
