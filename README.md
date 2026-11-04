# CRails Examples

> ⚠️ **EXPERIMENTAL FRAMEWORK, DO NOT USE IN PRODUCTION YET.**

Example applications for [CRails](https://github.com/OrelSokolov/crails) —
the Ruby on Rails port on Crystal. Each example is autonomous: it declares
its framework shards in its own `shard.yml` and resolves them from GitHub
tags via `shards install`.

## Examples

| Example | What it is |
|---|---|
| [`demo/`](demo/) | Full-stack demo app: mini-blog with accounts, validations, flash banners, chat with an SSE bot, Turbo Streams, and LiveView-style reactive views |
| [`hello_world/`](hello_world/) | The minimal app produced by `crails new` — baseline "Hello" page, first stop of the framework |
| [`rails_hello/`](rails_hello/) | 1:1 mirror of the Rails 8.1.1 reference app; one HTTP harness runs against both and both must pass the same oracle expectations |

## Technologies used

- **Crystal** >= 1.21
- Framework shards (each in its own [OrelSokolov](https://github.com/OrelSokolov?tab=repositories) repo):
  - `railties_cr` — the `crails` CLI, generators, app glue
  - `active_record_cr` — ORM, migrations, SQLite/PG adapters
  - `action_pack_cr`, `action_view_cr`, `erb_cr` — controllers, routing, ERB views
  - `action_cable_cr` — WebSockets
  - `turbo_cr` — Hotwire Turbo Streams
  - `live_view_cr` — LiveView-style reactive views
  - `devise_cr` — authentication (sessions, password digest)
  - `importmap_cr`, `propshaft_cr` — JS/CSS assets without a bundler
  - `active_job_cr`, `kiq_cr` — background jobs (see the main repo's benches)

## Running an example

```sh
cd demo
shards install
bin/crails server    # build + run, http://localhost:3000
```

## Relation to the main repo

This repository is embedded in [OrelSokolov/crails](https://github.com/OrelSokolov/crails)
as the `examples/` submodule pinned to `master`. Benchmarks and Rails
reference apps live in the main repo under `bench/`.
