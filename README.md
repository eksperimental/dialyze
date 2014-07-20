Mix.Task.Dialyze
================

Install
-------

For Elixir >= 0.14.3
```
git clone https://github.com/fishcakez/dialyze.git
cd dialyze
mix install
```
For Elixir < 0.14.3
```
git clone https://github.com/fishcakez/dialyze.git
cd dialyze
mix do compile, archive, local.install --force
```

Usage
-----
Carry out success typing analysis on any mix project:
```
mix dialyze
```
To just check the PLTs and skip success typing analysis:
```
mix dialyze --no-analyse
```
On subsequent calls for the same project checking the PLTs can be
skipped. This should only be done if the build environment's
dependencies have not changed since the PLTs were last checked:
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
