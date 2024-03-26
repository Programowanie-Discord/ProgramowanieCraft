# ProgramowanieCraft

## Clone

Clone the project into `ProgramowanieCraft` directory.

## Run

0. (Optional) Restore a backup file. The backup file must be in a backups directory.

    ```sh
    docker run --rm --volumes-from programowaniecraft-minecraft-1 -v /home/INSERT_BACKUPS_DIRECTORY:/backup bash -c "cd /data && tar xvf /backup/INSERT_BACKUP_FILENAME.tar --strip 1"
    ```

1. Create a `secrets` folder and add the secret files `db_password` and `discord_token`.

    ```sh
    mkdir secrets && cd secrets
    echo 'INSERT_DB_PASSWORD' > db_password
    echo 'INSERT_DISCORD_TOKEN' > discord_token
    ```

2. Open the `docker-compose.yml` file and fill out the values within the `CUSTOM CONFIG` block.

3. Create `minecraftdata` and `minecraftdbdata` volumes.

    ```sh
    docker volume create minecraftdata
    docker volume create minecraftdbdata
    ```

4. Run the server.

    ```sh
    docker-compose up -d --force-recreate
    ```

    You should restart the server after the first run (`spigot.yml` cannot be patched during the first run, because it doesn't exist).

## Backup

You can backup the `minecraftdata` volume by using the script in `scripts/backup.sh`. Please add it to cron for automatic backups (`scripts/cron`).

Backing up the database is possible, but the author of this project was too lazy to write the scripts here. Please refer to [the official MariaDB documentation](https://mariadb.com/kb/en/container-backup-and-restoration/ "MariaDB Knowledge Base").

## Plugins

- [Chunky](https://modrinth.com/plugin/chunky) (v1.3.136)
- [CoreProtect](https://modrinth.com/plugin/coreprotect) (v22.2)
- [DiscordSRV](https://modrinth.com/plugin/discordsrv) (v1.27.0)
- [EpicGuard](https://modrinth.com/plugin/epicguard) (v7.6.0)
- [FarmControl](https://modrinth.com/plugin/farmcontrol) (v1.2.5)
- [GrimAnticheat](https://hangar.papermc.io/GrimAnticheat/GrimAnticheat) (v2.3.61)
- [Insights](https://modrinth.com/plugin/insights) (v6.17.2)
- [LibreLogin](https://modrinth.com/plugin/libre-login) (v0.19.3)
- [LuckPerms](https://luckperms.net) (v5.4.121)
- [Pl3xMap](https://modrinth.com/plugin/pl3xmap) (v1.20.4-487)
- [SkinsRestorer](https://www.spigotmc.org/resources/skinsrestorer.2124/) (v15.0.7)
- [spark](https://spark.lucko.me/) (v1.10.60)
- [Vault](https://www.spigotmc.org/resources/vault.34315/) (v1.7.3)
- [WorldEdit](https://modrinth.com/plugin/worldedit) (v7.3.0)
- [WorldGuard](https://enginehub.org/worldguard) (v7.0.9)
