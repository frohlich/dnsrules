# dnsrules

A collection of DNS allowlist/blocklist rules for use with DNS-level ad blockers such as [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) and [Pi-hole](https://pi-hole.net/).

## Structure

```
allowlists/   # Rules that explicitly allow (whitelist) specific domains
```

## Allowlists

### `allowlists/copilot.txt`

Allowlist for [GitHub Copilot](https://github.com/features/copilot) and related GitHub services. Use this if your DNS blocker is blocking Copilot functionality.

Covers:
- Core GitHub domains (`github.com`, `api.github.com`)
- GitHub Copilot service domains (`githubcopilot.com` and subdomains)
- Copilot telemetry and proxy endpoints
- Copilot usage metrics/reports (Azure Front Door endpoints)

**Format:** AdGuard Home allowlist syntax (`@@||domain^`). DNS-level only — URL paths are not supported.

## Usage

In **AdGuard Home**: go to _Filters → DNS allowlists_ and add the raw URL of the desired file.

In **Pi-hole**: go to _Whitelist_ and add each domain individually, or use the [Teleporter](https://docs.pi-hole.net/core/pihole-command/#teleporter) to import.

## Contributing

Add new rule files under `allowlists/` or `blocklists/` (create the folder as needed). Follow the AdGuard filter syntax and include a brief comment header describing the purpose of the list.

