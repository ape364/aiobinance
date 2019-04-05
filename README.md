# aiobinance

[![PyPi](https://img.shields.io/pypi/v/aiobinance.svg)](https://pypi.org/project/aiobinance/)
[![License](https://img.shields.io/pypi/l/aiobinance.svg)](https://pypi.org/project/aiobinance/)
[![Build](https://travis-ci.com/ape364/aiobinance.svg?branch=master)](https://travis-ci.com/ape364/aiobinance)
[![Coveralls](https://img.shields.io/coveralls/ape364/aiobinance.svg)](https://coveralls.io/github/ape364/aiobinance)
[![Versions](https://img.shields.io/pypi/pyversions/aiobinance.svg)](https://pypi.org/project/aiobinance/)


[Binance.com](https://binance.com) [REST API](https://github.com/binance-exchange/binance-official-api-docs) async Python non-official wrapper. Tested only with Python 3.7. Alpha stage.

## Features

### API modules

Supports all API modules:

* [Account](https://github.com/binance-exchange/binance-official-api-docs/blob/master/rest-api.md#account-endpoints)
* [General](https://github.com/binance-exchange/binance-official-api-docs/blob/master/rest-api.md#general-endpoints)
* [Market](https://github.com/binance-exchange/binance-official-api-docs/blob/master/rest-api.md#market-data-endpoints)
* [Stream](https://github.com/binance-exchange/binance-official-api-docs/blob/master/rest-api.md#user-data-stream-endpoints)

## Installation

```sh
pip install -U aiobinance
```

## Usage
Register [Binance.com](https://binance.com) account and create free API key.

```python
import asyncio

from aiobinance import Client


async def main():
    c = Client('apikey', 'apisecret')
    try:
        print(await c.account.info())
        print(await c.general.exchange_info())
    finally:
        await c.close()


if __name__ == '__main__':
    asyncio.run(main())
```