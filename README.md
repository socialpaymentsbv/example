# Example app demonstrating potential bug in Erlang 23.4 Elixir or Mix

To reproduce run `mix compile` and then `mix ecto.load --force`.

Observed behaviour in Erlang 23.4: the `mix ecto.load ...` command recompiles 14 files.
Expected behaviour: no files should be recompiled.

The `--force` flag in this task means `do not ask for confirmation when loading data` but for some reason it seems to be passed to `mix compile`.

It wasn't the case in previous Erlang 22.4.
