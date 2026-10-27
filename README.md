# Identisure API Client Fixtures

[![MIT license][license-image]][license-url]

[license-image]: https://img.shields.io/badge/license-MIT-blue?style=flat-square
[license-url]: https://opensource.org/license/mit

Shared test fixtures for the Identisure API clients. Each client repository includes this repository as a git submodule at `fixtures/` and runs its end-to-end tests against these files.

Every file is a response body as returned by the Identisure REST API:

- `<provider>/auth_{pending,completed,failed,unknown}.json` for `bankid_se`, `bankid_no`, `freja`, `mitid`, `ftn` and `vipps`
- `<provider>/sign_completed.json` for `bankid_se`, `bankid_no`, `freja` and `mitid`
- `bankid_se/phone_auth_pending.json` and `bankid_se/verify.json`
- `age_verification/{pending,completed,failed,unknown}.json`
- `document/upload.json`
- `error.json`

The `unknown` fixtures use a status the clients do not know, to test forward compatibility.

After changing a fixture, update the submodule in each client repository:

```sh
git submodule update --remote fixtures
```
