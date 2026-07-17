# Matinee — Releases

Public release channel for **Matinee**, an Android TV VOD player.

- `stable/version.json` — stable channel manifest (default in-app update channel)
- `beta/version.json` — beta channel manifest
- APKs are attached to [GitHub Releases](../../releases)

The Matinee app polls the manifest for its configured channel via GitHub Pages:
`https://tomma-m.github.io/matinee-releases/<channel>/version.json`

Manifests are published automatically by the release workflow in the (private) source repository. Do not edit by hand except to roll back: re-pin `latest` to a previous release.
