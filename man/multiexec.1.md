# multiexec(1) -- run 2 or more commands in parallel

## SYNOPSIS

`multiexec` <command1> [<command2>] [<commandN> ...]

## DESCRIPTION

It runs two or more commands in parallel.

## EXAMPLE

If you dev environment has multiple processes running together, you can use `multiexec` to run them both under one process. In this example, we'll run Rails's development server with Guard.

```
multiexec "bundle exec rails s" "bundle exec guard"
```
