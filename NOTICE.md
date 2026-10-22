# N1 CarPlay for 2026 XPeng G6

Powered by OpenXPlay. This is an independent experimental adaptation; it is not an Apple or XPeng certified product.

- OpenXPlay-Relay: https://github.com/OpenXPlay/OpenXPlay-Relay (AGPL-3.0-only, with retained GPL-3.0-only components and attribution terms).
- OpenXPlay-Stream: https://github.com/OpenXPlay/OpenXPlay-Stream (AGPL-3.0-only and its retained attribution terms).
- N1 Wi-Fi helper: https://github.com/yizhixiaoheigou/DashPlay/blob/main/scripts/onecloud/board_phicomm_n1.py (GPL-3.0; original file retained with its documentation; license in packaging/DashPlay-LICENSE).
- Protocol components retain the upstream DiPlay/xcertplay notices and GPL terms. All original notices and licenses are included in the source snapshot and installed share/licenses.

Modifications: Linux HEVC Carlink negotiation, codec-locked transport and placeholder, window/stream-size touch handling, bounded video queue, N1 service/profile, local management and signed online upgrade/rollback tooling.

The update downloader also follows DashPlay's GitHub-first, configurable proxy-fallback approach, with independent implementation and verification for this release format. Reference: https://github.com/yizhixiaoheigou/DashPlay/blob/main/scripts/onecloud/update.py.

No accessory identity, private release key, user pairing, Wi-Fi password or certificate is distributed. The source corresponding to every build is included at share/admin/n1-source.tar.gz, accessible from the relay admin server at /n1-source.tar.gz. It is also provided next to the release bundle. See upstream-lock.json for exact source revisions.
