# with-temp-postgres

This is a handy script for temporarily running postgresql while you
execute a command: the DB is started against the specified data
directory (which must already exist), then the command is run, and
finally the DB is stopped again.

In conjunction with Nix, for example, this can be used to access data
from old DB installations, e.g.

```
nix-shell -p postgresql_9_6 --run "./with-temp-postgres /usr/local/var/postgres-9.6 psql -l"
```
