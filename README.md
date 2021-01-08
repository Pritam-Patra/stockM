# stockM

Use telegram to get stock updates regarding your portfolio of stocks.

## Usage

1. Download the [Telegram][1] application.
2. Search for the bot called **Stock Updates Slave** (*@stock_updates_bot*).
3. Find the list of helper commands using the `/` button.

### Basic Commands

1. Get price change for a single stock
    ```
    /get_px_change <ticker>
    ```

2. Get price change for multiple stocks
    ```
    /get_px_change <ticker1> <ticker2> <ticker3>
    ```

3. Get price change for your default portfolio of stocks. To do so, a `config.yml` file is required to be at the root of the project folder.

    Example `config.yml` file:
    ```
    DEFAULT_PORT:
      <STOCK1>: <STOCK1_HOLDINGS_QTY>
      AMZN: 1000
    ```

    This command will then be available in telegram.
    ```
    /default
    ```

### Deployment
This service is deployed on heroku using the `Procfile` listed in this
repository. To launch a service of your own, follow these steps:

1. Get an account with Heroku and install the heroku-cli
2. Create a new project

    ```bash
    heroku create <project_name>
    ```
3. To deploy this telegram bot, we need to set the telegram bot token as
an environment variable.

    ```bash
    heroku config:set TOKEN=<your_token_number>
    ```

4. Push the repo to the Heroku remote. Note that heroku will only build
if you push the main or master branch. No action will be taken if other
branches are pushed.

    ```bash
    git push heroku main
    ```

[1]: https://telegram.org/
