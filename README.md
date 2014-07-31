Mix.Task.Dialyze
================

Install
-------
Adds as a dependency:
```elixir
defp deps() do
  # It is likely to only desire dialyze for the `:dev` build environment,
  # and not for `:prod` and other build environments.
  [{:dialyze, "~> 0.1.0", only: [:dev]}]
end
```
Fetch and compile:
```
mix do deps.get, deps.compile
```

Usage
-----
Carry out success typing analysis on any mix project:
```
mix dialyze
```
To just check the PLT and skip success typing analysis:
```
mix dialyze --no-analyse
```
On subsequent calls for the same project checking the PLT can be
skipped. This should only be done if the build environment's
dependencies have not changed since the PLT were last checked:
```
mix dialyze --no-check
```
To skip compiling the project:
```
mix dialyze --no-compile
```
To turn on additional warnings:
```
mix dialyze --unmatched-returns --error-handling --race-conditions --underspecs
```
All switches are boolean and can be used in any combination, the default
is:
```
mix dialyze --compile --check --analyse --no-unmatched-returns --no-error-handling --no-race-conditions --no-underspecs
```
