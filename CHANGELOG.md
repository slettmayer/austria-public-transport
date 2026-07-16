# Changelog

## 1.0.1

- Add brand icon (`brand/` folder) so the integration shows its icon in the HA UI via the Brands Proxy API (HA 2026.3+)

## 1.0.0

- Relaunched as **Austria Public Transport (Wiener Linien & ÖBB)** in a standalone (non-fork) repository
- Integration domain renamed to `austria_public_transport` to reflect both Wiener Linien and ÖBB support (existing installs must be re-added)
- Documentation now covers UI (config flow) setup; corrected legacy YAML platform references
- Originally based on wl_monitor by @0Paul89 (used with permission); licensed under MIT

## 0.9.2

- Fix product bitmask in `oebb_service_alerts` to include Westbahn and other private operators

## 0.9.1

- Fix `direct_only` filter in `oebb_trip_search` -- use correct OeBB API parameter (`maxChg` instead of `numChg`)

## 0.9.0

- Add optional `direct_only` parameter to `oebb_trip_search` to filter for direct connections only

## 0.8.0

- New service: `oebb_service_alerts` -- fetch current OeBB service alerts and disruptions via HimSearch
- Supports product type filtering via bitmask (e.g., only long-distance trains)

## 0.7.0

- Add optional `time` and `time_mode` fields to `oebb_trip_search` for future trip planning
- `time` accepts local time (CET/CEST); defaults to current time when omitted
- `time_mode` selects between "departure" (default) and "arrival" search

## 0.6.0

- Add OeBB (Austrian Federal Railways) service calls via the OeBB Scotty API
- New service: `oebb_search_station` -- search stations by name to find station IDs
- New service: `oebb_station_board` -- fetch departures/arrivals at an OeBB station (by ID or name)
- New service: `oebb_trip_search` -- search train connections between two stations (by ID or name)
- Add unit tests for OeBB API client (21 tests)
- Add integration tests against real OeBB API (4 tests, excluded from CI)
- Update documentation: README, CLAUDE.md, architecture, domain, testing, and tech stack docs

## 0.5.0

- Automate releases: version change in manifest.json triggers tag + GitHub release after validation passes
- Add dependabot auto-bump: patch version and changelog entry created automatically on Dependabot PRs
- Add gate job to Validate workflow for branch protection
- Add Dependabot config for GitHub Actions
- Add CHANGELOG.md with historical release entries

## 0.4.1

- Fix: service rejecting integer stop_id values

## 0.4.0

- Modernize repo: DataUpdateCoordinator, config flow, tests, CI
- Extract shared API helper, add const.py, improve code quality
- Repo hygiene: fix .gitignore, add LICENSE, clean up dead code

## 0.3.0

- Add English translations as fallback

## 0.2.0

- Add fetch_departures service action
- Small code polish of sensor

## 0.1.0

- Initial cleanup after fork
