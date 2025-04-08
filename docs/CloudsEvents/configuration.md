---
weight: 3
---
# Configuration

After you've set the basic configuration you may now customize it.


## Setup the Database

Setting up a database is important since it's used for <i>temporary player informations</i> and <i>player statistics</i> storage.

=== "H2"

	1. Set `"H2"` in your `database-type` field in the `config.yml` file.

=== "MySQL"

	1. Set `"MySQL"` in your `database-type` field in the `config.yml` file.
	2. Set your `mysql-host` in the `config.yml` file, it's ```IP:PORT``` format.
	3. Set your `mysql-database-name` in the `config.yml` file, leaving it as default should be good.
	4. Set your `mysql-username` and `mysql-password` in the `config.yml` file.

!!! tip

	It's recommended to choose MySQL as your database since it's much more stable and optimized.

## Configuration Files

If you're interested in the default configuration files, you can copy them here:

=== "Config"

    ``` yaml title="config.yml" 
        --8<-- "assets/config.yml"
    ```

=== "Messages"

    ``` yaml title="messages.yml"
        --8<-- "assets/messages.yml"
    ```

=== "Map Config"
    ```yaml title="mapConfig.yml"
        --8<-- "assets/mapConfig.yml"
    ```