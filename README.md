# Example app demonstrating potential bug in Erlang 23.4 Elixir or Mix

To reproduce run `mix compile` and then `mix ecto.load --skip-if-loaded --force`.

Observed behaviour in Erlang 23.4: the `mix ecto.load ...` command recompiles 14 files.
Expected behaviour: no files should be recompiled.

The `--force` flag in this task means `do not ask for confirmation when loading data` but for some reason it seems to be passed to `mix compile`.

It wasn't the case in previous Erland 22.4.


# Example

To start your Phoenix server:

  * Install dependencies with `mix deps.get`
  * Create and migrate your database with `mix ecto.setup`
  * Install Node.js dependencies with `npm install` inside the `assets` directory
  * Start Phoenix endpoint with `mix phx.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](https://hexdocs.pm/phoenix/deployment.html).

## Learn more

  * Official website: https://www.phoenixframework.org/
  * Guides: https://hexdocs.pm/phoenix/overview.html
  * Docs: https://hexdocs.pm/phoenix
  * Forum: https://elixirforum.com/c/phoenix-forum
  * Source: https://github.com/phoenixframework/phoenix
