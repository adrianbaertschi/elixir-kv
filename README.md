# Distributed key-value store written in Elixir
My code following the official elixir tutorial [Introduction to Mix](https://elixir-lang.org/getting-started/mix-otp/introduction-to-mix.html).

Umbrella project with two apps:
- [kv](apps/kv): Core Key-value store module
- [kv_server](apps/kv_server) TCP Server for handling requests

Run all tests:
`mix test`

Build and run node 1:
```
MIX_ENV=prod mix release foo
_build/prod_rel/foo/bin/foo start
```

Build and run node 2:
```
MIX_ENV=prod mix release bar
_build/prod_rel/bar/bin/bar start
```

Use
```
telnet 127.0.0.1 4040

CREATE shopping
OK

PUT shopping milk 1
OK

PUT shopping eggs 3
OK

GET shopping milk
1
OK

DELETE shopping eggs
OK
```