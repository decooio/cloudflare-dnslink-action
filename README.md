# Cloudflare IPFS Dnslink Action

Create or update Cloudflare domain's TXT record dnslink value to IPFS hosted website's CID.

## Usage via Github Actions

Add [CLOUDFLARE_TOKEN](https://developers.cloudflare.com/api/tokens/create) and CLOUDFLARE_ZONE to the [repository secrets](https://docs.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets).

```yaml
name: example
on:
  pull_request:
    type: [opened, reopened]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: decooio/cloudflare-dnslink-action@v1.0.0
        with:
          name: "ipfs.example.com"
          cid: "QmezqWkdy2tTC6fBrrvgm7dRgQLZPmMQRTuJMaSVZFYUZg"
          token: ${{ secrets.CLOUDFLARE_TOKEN }}
          zone: ${{ secrets.CLOUDFLARE_ZONE }}
```

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE).
