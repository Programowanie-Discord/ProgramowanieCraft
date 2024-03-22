# ProgramowanieCraft

## Clone

Clone the project into `ProgramowanieCraft` directory.

## Run

0. (Optional) Restore a backup file.

    ```sh
    docker run --rm --volumes-from programowaniecraft-minecraftdata-1 -v /home/INSERT_BACKUPS_DIRECTORY:/backup bash -c "cd /data && tar xvf /backup INSERT_BACKUP_FILENAME.tar --strip 1"
    ```

1. Search (`CTRL+F`) for `# FILL!!!` comments in
    - `plugins/DiscordSRV/config.yml`,
    - `plugins/DiscordSRV/linking.yml`
    - `plugins/DiscordSRV/synchronization.yml`,
    - `plugins/dynmap/configuration.txt`,
    - `docker-compose.yml`,  
and fill the values.

2. Create a `minecraftdata` volume.

    ```sh
    docker volume create minecraftdata
    ```

3. Run the server.

    ```sh
    docker-compose up -d --force-recreate
    ```

## Backup

You can backup this project by using the script in `scripts/backup.sh`. Please add it to cron for automatic backups (`scripts/cron`).

## Plugins

- [CoreProtect](https://www.spigotmc.org/resources/coreprotect.8631/) (v22.2)
- [DiscordSRV](https://www.spigotmc.org/resources/discordsrv.18494/) (v1.27.0)
- [dynmap](https://www.spigotmc.org/resources/dynmap.274/) (v3.7-beta-4)
- [LuckPerms](https://www.spigotmc.org/resources/luckperms.28140/) (v5.4.121)
- [SkinsRestorer](https://www.spigotmc.org/resources/skinsrestorer.2124/) (v15.0.7)
- [Vault](https://www.spigotmc.org/resources/vault.34315/) (v1.7.3)
- [WorldEdit](https://dev.bukkit.org/projects/worldedit/) (v7.3.0)
- [WorldGuard](https://dev.bukkit.org/projects/worldguard) (v7.0.9)
