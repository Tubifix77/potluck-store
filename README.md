# Potluck store

The curated list of apps for [Potluck](https://github.com/Tubifix77/potluck)'s store: sandboxed apps
(WebAssembly guests) that a Potluck cell's owner can install from the dashboard's Library, under
"Apps from GitHub". The store is off in every cell until its owner turns it on.

- `feed.json` is the list. `feed.sig` is the store key's Ed25519 signature over it; Potluck carries the
  key's public half and shows no list whose signature does not verify.
- `apps/` holds apps published here. An app can live in any GitHub repository; the list only points to it.

Being on the list vouches for nothing a review did not. Every cell still checks each app's module against
its author's signature, pins the author's key to the app's repository on the first install (a changed key
is refused), and lets the owner choose which of the cell's resources the app may read. An app writes
nothing but its own outputs.

## Publishing an app

Put `potluck-app.json` beside your module, as Potluck's developer manual describes
([DEVELOPING-APPS.md](https://github.com/Tubifix77/potluck/blob/main/DEVELOPING-APPS.md), "Publishing a
guest for any cell"). Any owner can install it by typing your repository in. To be on this list, open a pull
request adding it to `feed.json`; the list is re-signed when it is merged.

This repository was set up by Claude (an AI model) for the project's owner.

## Licence

Apache-2.0, as Potluck. The example `overheat_alarm` is built from Potluck's `guests/overheat_alarm.rs`.
