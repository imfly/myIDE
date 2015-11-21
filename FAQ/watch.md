#### `error: watch ENOSPC` when I run the watch task  by `gulp` or `grunt`? 

```
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

http://stackoverflow.com/questions/16748737/grunt-watch-error-waiting-fatal-error-watch-enospc