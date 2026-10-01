# DevOps Notes

My DevOps learning project.

This line was added from the first local repository.

## Disclaimer
This configuration is intended solely for local development and training purposes. The server is bound to the address 127.0.0.1 (accessible only from the local machine) and openly exposes the contents of the `linux/` directory. Do not use this script or unit file for public-facing websites without first configuring access restrictions and hiding system files.

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

## How to enable and test automatic start at boot
`sudo systemctl enable notes`
`sudo systemctl is-enabled notes`
### If you want to enable autostart and immediately launch the service with one command
`sudo systemctl enable --now notes`

## How to check an HTTP response using curl
`curl http://127.0.0.1:8080`
### Optional
`sudo ss -tupln | grep ':8080'`
