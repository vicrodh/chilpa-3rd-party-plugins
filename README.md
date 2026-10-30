<img width="100%" alt="Chilpa 3rd Party Plugins: community-made plugins and integrations" src="assets/chilpa-3rdparty-plugins.png" />

> These plugins meet [Chilpa's requirements](#rules-for-listing-a-plugin) to
> be listed in this catalog, but Chilpa does not endorse them. Their code and
> how they work are the responsibility of their authors and of the people who
> use them.

# Chilpa 3rd-party plugins

This catalog, maintained by [vicrodh](https://github.com/vicrodh), lists
independently published plugins for [Chilpa](https://github.com/vicrodh/chilpa), a native music
player for local libraries and self-hosted servers
([chilpa.app](https://chilpa.app)). The plugins use Chilpa's native plugin
API, documented in the [SDK](https://github.com/vicrodh/chilpa-plugins-sdk). It is separate from
[Chilpa's official catalog](https://github.com/vicrodh/chilpa-plugins).
Listed plugins are **third-party, with Chilpa verification and validation**.
Inclusion here does not make them official plugins or imply affiliation with a
service provider. Validation evidence accompanies each listed release.

## Disclaimer

Each plugin here is written and maintained by its author. Its code is not part
of Chilpa, and neither Chilpa nor its author is responsible for it or for how
it is used. A plugin that relies on reverse engineering does so under its
author's responsibility, and using it is the responsibility of whoever
installs it. The validation recorded here shows that a package installs and
works in Chilpa; it does not review the plugin's code or its standing with any
service.

## Rules for listing a plugin

Every plugin in this catalog follows these rules. The full text, and how to
submit a plugin, are in [CONTRIBUTING.md](CONTRIBUTING.md).

1. Open source, and credit for the work it builds on. A closed-source plugin
   is possible only after discussing it with Chilpa's author, and with public
   Terms of Service and a public Privacy Policy.
2. No piracy: strictly no stream-ripping tools.
3. Credentials are stored as the SDK's
   [Credentials](https://github.com/vicrodh/chilpa-plugins-sdk/blob/main/wiki/Credentials.md) page describes, and a plugin
   never reads, or tries to read, another plugin's credentials.
4. A person writes or signs the pull request, in plain human text with no
   emojis, even if the plugin was generated with AI.
5. A change the plugin needs in Chilpa's core goes to
   [chilpa](https://github.com/vicrodh/chilpa) as a pull request, justified
   as reusable by other plugins.
6. Reverse engineering is the responsibility of the plugin's author, and
   using the plugin is the responsibility of whoever installs it.
7. Telemetry only with an opt-in or opt-out switch visible in the plugin's
   settings, disclosed from installation with Terms of Service, a Privacy
   Policy, and a README that explains the data flow and disclaims liability.

## Install

Chilpa offers this catalog by default, alongside the official one. Its plugins
appear in **Settings > Plugins** with a **Third-party** tag, and **Manage**
lists the catalog under **Third-party plugins**, where it can be refreshed.
Select **Install**, review the requested permissions and enable the plugin.
Nothing is installed or enabled on its own, and each download has a SHA-256
checksum. The catalog's address is:

```text
https://raw.githubusercontent.com/vicrodh/chilpa-3rd-party-plugins/main/index.json
```

## Plugins

| Plugin | Author | Source and downloads | Platform | Requirements |
| --- | --- | --- | --- | --- |
| Apple Music | [ShinnyCharizard](https://github.com/ShinnyCharizard) | [apple-music-source](https://github.com/ShinnyCharizard/apple-music-source) | Linux x86_64 | Apple Music subscription; glibc 2.42 and GLIBCXX_3.4.30 or later; Apple libraries installed explicitly in settings. |
| Tidal | [vicrodh](https://github.com/vicrodh) | [chilpa-pg-tidal](https://github.com/vicrodh/chilpa-pg-tidal) | Linux x86_64 | Chilpa 0.1.0-beta; a Tidal account with a subscription for full playback. |
| Spotify | [vicrodh](https://github.com/vicrodh) | [chilpa-pg-spotify](https://github.com/vicrodh/chilpa-pg-spotify) | Linux x86_64 / macOS Apple Silicon | A host with native process support; Premium for playback; personal Client ID recommended. |
| Deezer | [ShinnyCharizard](https://github.com/ShinnyCharizard) | [deezer-source](https://github.com/ShinnyCharizard/deezer-source) | Linux x86_64 / macOS Apple Silicon | Your own Deezer session; subscription and track availability determine audio quality. |

The Tidal plugin is independent of the service provider and retains its
GPL-3.0-or-later license.
It provides library browsing, search, discovery, playlists and playback through
its own account connection. Account credentials remain in the plugin's private
data; its README describes storage, permissions and playback limits.

The Spotify plugin is independently published under MIT. Its README and
bundled licenses credit Carmine Paolino's Spotifast. It is also a working example in the SDK's
[native process guide](https://github.com/vicrodh/chilpa-plugins-sdk/blob/main/wiki/Native-Plugins.md#native-source-example).
Its separate Web and playback approvals, quotas, account storage and tested
platform limits are documented in the plugin repository.

## Catalog format

The native version-1 JSON catalog records a plugin ID, author, repository,
version, API range, immutable versioned release URL and SHA-256. A package
can be listed only after that exact archive is published and checked. The catalog itself is MIT
licensed; individual plugins keep their own licenses.

## Independent repositories

Plugin authors can
host a version-1 `index.json` in a separate repository and distribute its URL
directly. Chilpa can add that URL alongside this catalog and the official one.
Those releases do not carry this catalog's Chilpa validation. They still need
valid SDK manifests, supported runtimes and permissions, compatible API versions
and matching package checksums to install and run.

The public [SDK and authoring documentation](https://github.com/vicrodh/chilpa-plugins-sdk)
defines the plugin contract. A detailed independent-repository guide is not
yet available.
