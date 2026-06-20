# Teams Storage Migration Guide

This guide explains how to migrate your **Teams** plugin data between supported storage backends.

## What migration does

The plugin includes a built-in migration system that moves your current team data from the active storage backend to another one.

Supported storage types:

- `yaml`
- `sqlite`
- `h2`
- `mysql`
- `mariadb`
- `postgresql`

When migration starts, the plugin:

1. Reads the **currently loaded team data**
2. Applies the new storage settings you entered
3. Connects to the target storage backend
4. Writes the current team data into that backend
5. Saves the new storage settings
6. Reloads the plugin

If migration fails, the plugin restores the previous storage configuration.

## Important notes before migrating

Before starting migration, make sure you:

- Back up your full `plugins/Teams` folder
- Avoid team changes while migration is running
- Make sure your current data is loading correctly
- Make sure remote database credentials are correct if using MySQL, MariaDB, or PostgreSQL
- Make sure the server has internet access the first time a JDBC driver is needed
