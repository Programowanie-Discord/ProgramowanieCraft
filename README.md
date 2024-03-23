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

3. Create `minecraftdata` and `databasedata` volumes.

    ```sh
    docker volume create minecraftdata
    docker volume create databasedata
    ```

4. Run the server.

    ```sh
    docker-compose up -d --force-recreate
    ```

## Backup

You can backup the `minecraftdata` volume by using the script in `scripts/backup.sh`. Please add it to cron for automatic backups (`scripts/cron`).

Backing up the database is possible, but the author of this project was too lazy to write the scripts here. Please refer to [the official MariaDB documentation](https://mariadb.com/kb/en/container-backup-and-restoration/ "MariaDB Knowledge Base").

## Plugins

- [CoreProtect](https://www.spigotmc.org/resources/coreprotect.8631/) (v22.2)
- [DiscordSRV](https://www.spigotmc.org/resources/discordsrv.18494/) (v1.27.0)
- [dynmap](https://www.spigotmc.org/resources/dynmap.274/) (v3.7-beta-4)
- [LuckPerms](https://www.spigotmc.org/resources/luckperms.28140/) (v5.4.121)
- [SkinsRestorer](https://www.spigotmc.org/resources/skinsrestorer.2124/) (v15.0.7)
- [Vault](https://www.spigotmc.org/resources/vault.34315/) (v1.7.3)
- [WorldEdit](https://dev.bukkit.org/projects/worldedit/) (v7.3.0)
- [WorldGuard](https://dev.bukkit.org/projects/worldguard) (v7.0.9)
- [AuthMe](https://www.spigotmc.org/resources/authme-reloaded.6269/) (v5.6.0-beta2)
