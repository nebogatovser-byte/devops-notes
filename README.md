# DevOps Notes

My DevOps learning project.

This line was added from the first local repository.
## File description
- `linux/run-server.sh` — Bash-скрипт, который через `exec` заменяет себя на `python3`. Благодаря `exec` Python становится главным процессом сервиса, а не дочерним.
- `linux/notes.service` — systemd unit для запуска HTTP-сервера.

## How to install a unit in /etc/systemd/system/
`sudo cp linux/notes.service /etc/systemd/system/notes.service`

## How to perform a daemon-reload, start, stop, and check a service
`sudo systemctl daemon-reload`
`sudo systemctl start notes`
`sudo systemctl stop notes`
`sudo systemctl status notes`

## How to enable and test remote start
`sudo systemctl enable notes`
`sudo systemctl is-enable notes`

## How to check an HTTP response using curl
`curl curl http://127.0.0.1:8080`
# Optional
`sudo ss -tupln | grep ':8080'`
