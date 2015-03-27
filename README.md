# multiexec

**Run 2 or more commands in parallel.**

```
npm install -g multiexec
```

```
multiexec "command 1" "command 2"
```

<br>

## Practical use

Use `multiexec` to use [browser-sync](http://browsersync.io/) with another build process. In this example, we'll use [Jekyll](http://jekyllrb.com/)—this effectively makes for a LiveReload-enabled Jekyll dev environment.

```
$ multiexec "jekyll build --watch" "browser-sync start --server _site --files='_site/*, _site/*/*'"

1 running jekyll build --watch
2 running broswer-sync start --server ...
2  [BS] Access URLs:
2   --------------------------------------
2         Local: http://localhost:3005
2      External: http://192.168.1.187:3005
2   --------------------------------------
2  [BS] Serving files from: _site
2  [BS] Watching files...
1  Configuration file: /home/me/project/_config.yml
1              Source: /Uome/me/project
1         Destination: /Uome/me/project/_site
1        Generating... done.
```

If you dev environment has multiple processes running together, you can use `multiexec` to run them both under one process. In this example, we'll run [Rails](http://rubyonrails.org/)'s development server with [Guard](rubygems.org/gems/guard) for auto-reloading.

```
multiexec "bundle exec rails s" "bundle exec guard"
```

<br>

## Thanks

MIT license
