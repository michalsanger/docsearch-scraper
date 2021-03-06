Hello you,

## Install and use the scraper without Docker

We do recommend [pipenv][1] to install the whole python environment

- [Install pipenv][2]
- `pipenv install`
- `pipenv shell`

## Installing Chrome Headless

Websites that need JavaScript for rendering are passed through ChromeDriver.
[Download the version][4] suited to your OS and then update the
`CHROMEDRIVER_PATH` in your `.env` file.

You should be ready to go.

## Run the tests

To run the full test suite, run `./docsearch test`.

# Special instructions for Algolia employees

## Ready to deploy

If you are Algolia employee and want to manage a DocSearch account, you'll need
to copy and paste [the required variables][3] in your `.env` file.

Ping the @DocSearch team to get access to those credentials.

Clone the configurations repository in your docsearch-scraper directory. Command
to run from the scraper root:

```bash
git clone git@github.com:algolia/docsearch-configs.git configs/public
```

The CLI will then have more commands for you to run.

## Reason of a fail from the docker image

To spot why a crawl fail without watching the logs, we have defined some custom 
exit status:

| Exit code | Reason                                         |
|:---------:|------------------------------------------------|
|     3     | No record extracted from the crawl             |
|     4     | Too much hits returned from the crawl          |
|     5     | The configuration provided is not a valid JSON |


[1]: https://github.com/pypa/pipenv
[2]: https://pipenv.readthedocs.io/en/latest/install/#installing-pipenv
[3]: ./.env.example
[4]: http://chromedriver.chromium.org/downloads
