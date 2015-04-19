# multiexec(1) -- run 2 or more commands in parallel

## SYNOPSIS

`multiexec` <command1> [<command2>] [<commandN> ...]

## DESCRIPTION

It runs two or more commands in parallel.

When one of the subprocesses exits with an error code, all the subprocesses will be terminated.

## OPTIONS

* `commandN` :
  A command to be executed, including its arguments. This command will be passed onto `sh -c`, and so it will be shell-separated as needed. 

## EXAMPLE

If you dev environment has multiple processes running together, you can use `multiexec` to run them both under one process. In this example, we'll run Rails's development server with Guard.

```
multiexec "bundle exec rails s" "bundle exec guard"
```
