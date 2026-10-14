# AuraGIS basemap archives

Prebuilt [PMTiles](https://docs.protomaps.com/pmtiles/) basemap archives used by
AuraGIS Pro. **This repository holds no source code** — only these notes and the
archives attached to its releases.

## Attribution and licence

The archives are cut from [Protomaps](https://protomaps.com)' daily planet build,
which is derived from OpenStreetMap.

> Map data © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors,
> available under the [Open Database License](https://opendatacommons.org/licenses/odbl/).

The ODbL binds **the database**, not software that reads it. Each archive here is a
bounding-box subset of a public ODbL file and carries no AuraGIS intellectual
property, so it is redistributed under the same terms it arrived under. Any
further redistribution must keep this attribution.

`LICENSE` declares the two régimes this repository holds: the archives under the ODbL
as above, and the repository's own text — these notes and anything later committed
beside them — reserved on ADR-018 §3's model. **D40.** A licence that is silent about
the largest thing in a repository is read as covering it, so the carve-out for the
release assets is §2 of that file rather than a footnote to it.

## Verifying a download

Every release records each archive's SHA-256 below and in the release notes. The
application verifies size and then hash before installing an archive, and refuses
one that does not match, so a truncated or substituted download fails closed
rather than drawing a wrong map.

```sh
sha256sum australia-towns-and-regions-20261011.pmtiles
```

## What each archive is

| archive | area | zooms | tiles | bytes |
| --- | --- | --- | --- | --- |
| `australia-towns-and-regions-20261011.pmtiles` | Australia, `96 -44 169 -9` | z0–11 | 127,387 | 117,637,297 |

Built with AuraGIS Pro's own extract against `build.protomaps.com/20261011.pmtiles`.

**Byte sizes are not reproducible across days.** The same bounding box and zoom
range cut from a later planet build yields a correct archive with a different
hash, so each release pins the artefact it actually shipped rather than a recipe
for rebuilding it.
