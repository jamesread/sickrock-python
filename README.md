<div align = "center">
  <img alt = "project logo" src = "logo.png" width = "128" />
  <h1>SickRock Python lib/cli</h1>

  Build nocode data base webapps on real databases

[![Maturity Badge](https://img.shields.io/badge/maturity-Sandbox-yellow)](#none)
[![Discord](https://img.shields.io/discord/846737624960860180?label=Discord%20Server)](https://discord.gg/jhYWWpNJ3v)

</div>

Python client and CLI for the [SickRock](https://github.com/jamesread/SickRock) Connect API.

## Install

```bash
pip install sickrock_client
```

## CLI

The package installs a `sickrock` command:

```bash
sickrock info
sickrock -j info
sickrock insert -t default -f type TASK -f timestamp "2026-06-12 12:00:00"
sickrock call Init
sickrock list-operations
sickrock help insert
```

Configuration defaults to `/etc/SickRockClient/settings.env` and supports `SICKROCK_URL`, `BEARER_TOKEN`, and `VERIFY_SSL` (or `verify-ssl=false` in the config file). Use `-k` or `--no-verify-ssl` to skip certificate verification. Use `-j` or `--json` for JSON-only output.

## Library

```python
from sickrock_client import SickRockClient

client = SickRockClient("https://example.com", "token")
item = client.create_item("default", {"type": "TASK", "timestamp": "2026-06-12 12:00:00"})
info = client.init()
```
