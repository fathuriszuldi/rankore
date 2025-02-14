<p align="center">
    <img width="500" height="auto" src="./assets/et6QQbt.png" alt="WiseMan" />
</p>

## rankore - Discord Bot 🤖
A discord bot to track user activity in a Discord server.
This bot is currently tracking voice and text user activity into a Discord server.<br>

[Invite me!](https://discord.com/oauth2/authorize?client_id=1161409490369912924&scope=bot)
 or Join the official [rankore Discord server](https://discord.gg/RezDWZwKCT)!

## Prerequisites
1. Rust 1.81.0
2. Cargo  1.84.0

## Installation
1. Clone this Repository
2. Install the db from the docker
```bash
docker compose up -d
```
3. Add the DB to env
```bash
 export DATABASE_URL="postgres://postgres:password@localhost:5431/mydb"
```
4. Migrate the DB
```bash
cargo sqlx migrate run
```
5. Build the app
```bash
cargo build
```
6. Prepare the DB
```bash
cargo sqlx prepare
```
7. Add your Discord token
```bash
export DISCORD_TOKEN=<Your Token Here>
```
8. Run run.sh
```bash
./run.sh
```
or you can use screen
```bash
screen ./run.sh
```


## Commands
- `!leaderboard`: List the users and their points, from the most active to the less active;
- `!download_leaderboard`: get a file .xlsx containing a table with all the users and related scores
- `!set_prefix [PREFIX]`: Set the prefix for the Discord server in which the bot is running; (After this command the default `!` prefix will not be active, replaced by the one you set)
- `!get_prefix [PREFIX]`: Get the prefix for the Discord server in which the bot is running, (This command will be always available also with the default prefix `!`)
- `!set_welcome_msg [STRING]`: Set the welcome message
- `!reset_scores`: Reset leaderboard scores
- `!set_voice_multiplier [INTEGER]`: set the multiplier to calculate the points for the voice activity for a user in a Discord server. greater the multiplier, greater will be the wait to add a point to that user. For example, if the admin sets the multiplier to 5, the bot will wait 5 seconds before incrementing 1 point to the user
- `!set_text_multiplier [INTEGER]`: set the multiplier for each message, this is simply the points for each message
- `!multipliers`: shows the `set_voice_multiplier` and the `set_text_multiplier`
- `!help`: Get this help message (This command will be always available also with the default prefix `!`)

Ensure to have a `#welcome` channel existing in the Discord server!
