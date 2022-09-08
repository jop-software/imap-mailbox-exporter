# Imap Mailbox Exporter

> Export the amount of mails in a mailbox for use in prometheus.

## Usage

### Configuration

```dotenv
IMAP_SERVER=""
IMAP_USERNAME=""
IMAP_PASSWORD=""
```

### Probe

```txt
http://127.0.0.1:9101/probe?target=INBOX
```

### Provided metrics

```txt
# HELP probe_mailbox_count Displays the count of mails found in the mailbox
# TYPE probe_mailbox_count gauge
probe_mailbox_count 0
```

### Configuration

The `imap-mailbox-exporter` can be configures with a `config.yaml` file and environment variables.

```yaml
server:
- hostname: 'hostname'
  port: '1234'
  accounts:
    - username: 'e@mail.com'
      password: 'env:E_AT_MAIL_COM_PASSWORD'
```

You can use environment variables with the `env:VARIABLE_NAME` directive in YAML.

The configuration file is expected in `./config.yaml` relative to the `imap-mailbox-exporter` binary.

### Example Usage

You can find a example docker compose configuration.

Make sure to update `examples/imap-exporter.env` with your imap credentials.

**Start the example container**

```shell
pushd examples

docker compose pull
docker compose up -d
```

## License

This project is licensed under the [MIT License](./LICENCE)

<div align="center">
    <span>&copy; 2022, jop-software Inh. Johannes Przymusinski</span>
</div>