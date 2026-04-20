### android
```
19:32:47 web.1  | Started GET "/exercise_entries/new?date=2026-04-16" for 127.0.0.1 at 2026-04-16 19:32:47 +0200
19:32:47 web.1  | Processing by ExerciseEntriesController#new as HTML

19:32:51 web.1  | Started POST "/exercise_entries" for 127.0.0.1 at 2026-04-16 19:32:51 +0200
19:32:51 web.1  | Processing by ExerciseEntriesController#create as TURBO_STREAM
19:32:51 web.1  | Redirected to http://10.0.2.2:3000/days/2026-04-16

19:32:51 web.1  | Started GET "/days/2026-04-16" for 127.0.0.1 at 2026-04-16 19:32:51 +0200
19:32:51 web.1  | Processing by DaysController#show as TURBO_STREAM

19:32:51 web.1  | Started GET "/days/2026-04-16" for 127.0.0.1 at 2026-04-16 19:32:51 +0200
19:32:51 web.1  | Processing by DaysController#show as HTML

*flash is not shown*
```

### ios
```
20:27:29 web.1  | Started GET "/exercise_entries/new?date=2026-04-16" for ::1 at 2026-04-16 20:27:29 +0200
20:27:29 web.1  | Processing by ExerciseEntriesController#new as HTML

20:27:32 web.1  | Started POST "/exercise_entries" for ::1 at 2026-04-16 20:27:32 +0200
20:27:32 web.1  | Processing by ExerciseEntriesController#create as TURBO_STREAM
20:27:32 web.1  | Redirected to http://localhost:3000/days/2026-04-16

20:27:32 web.1  | Started GET "/days/2026-04-16" for ::1 at 2026-04-16 20:27:32 +0200
20:27:32 web.1  | Processing by DaysController#show as TURBO_STREAM

*flash is shown*
```

### However
- if we disable the `context: "modal"` section in ConfigurationsContoller#ios, we'll get double requests and lose the flashes on ios, too
- if we add a path configuration with `context: modal` for android (tried in a separate app), we'll still have double requests
