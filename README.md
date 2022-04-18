<h1 align="center">
  <img src="https://github.com/projectdiscovery/cloudlist/blob/main/static/cloudlist-logo.png" alt="cloudlist" width="200px">
  <br>
</h1>

<h4 align="center"><a href="https://github.com/projectdiscovery/cloudlist-action">Cloudlist Action</a> makes it easy to orchestrate <a href="https://github.com/projectdiscovery/cloudlist">cloudlist</a> with GitHub Action.</h4>



Example Usage
-----

**GitHub Action running `cloudlist`**

```yaml
      - name: 🌥 Cloudlist - List them all
        uses: projectdiscovery/cloudlist-action@main
        with:
          config: cloudlist-config.yaml
```

**Example workflow**: `.github/workflows/cloudlist.yml`


```yaml
name: 🌥 Cloudlist - List them all

on:
    schedule:
      - cron: '0 0 * * *'
    workflow_dispatch:

jobs:
  cloudlist-scan:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-go@v3
        with:
          go-version: 1.17

      - name: 🌥 Cloudlist - List them all
        uses: projectdiscovery/cloudlist-action@main
        with:
          config: cloudlist-config.yaml
```


Available Inputs
------

| Key      | Description                           | Required |
|----------|---------------------------------------|----------|
| `config` | Config file to use with cloudlist     | true     |
| `output` | File to save output result            | false    |
| `json`   | Format to save of output file         | false    |
| `flags`  | Additional cloudlist CLI flags to use | false    |
