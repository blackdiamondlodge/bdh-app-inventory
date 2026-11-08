# bdh-app-inventory

Black Diamond Hub app: kitchen inventory with QR codes. Moved out of
[BlackDiamondHub](https://github.com/blackdiamondlodge/BlackDiamondHub) and
installed into the hub through the `blackdiamondhub.plugins` entry point
(see [bdh-sdk](https://github.com/blackdiamondlodge/bdh-sdk)).

Page: `/inventory/` (sign-in required). It has no homepage tile; open it by URL.

Item photos are stored in the hub's `MEDIA_ROOT`.

## Development

CI (`.github/workflows/ci.yml`) uses the reusable `app-ci.yml` from
bdh-sdk. It builds the wheel, installs it next to the hub, then runs
`hub_smoke`, the app tests and the selenium tests.

To release, bump `version` in `pyproject.toml`. When that lands on
`main`, `release.yml` tags it and publishes the wheel, and the release
notes include the hashed line for the hub's `sites/<site>/apps.txt`.
