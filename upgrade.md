# Upgrade

## From the same major version

- Create a new back up of all files and directories
- Download the latest version from the [official repo](https://github.com/BoidCMS/BoidCMS)
- Extract the zip.
- Replace existing files with the new files
- Test the site

## From different major version

- Check the release notes
- Test the upgrade on a staging site
- Create a new back up of all files and directories
- Uninstall all the plugins
- Download the latest version from the [official repo](https://github.com/BoidCMS/BoidCMS)
- Extract the zip.
- Replace existing files with the new files
- Test the site thoroughly
- Re-install all the plugins, one at a time


Because BoidCMS does not use a database by default, you don't have to run any database migrations.

If you experience problems after the upgrade, you can restore from your backup.
