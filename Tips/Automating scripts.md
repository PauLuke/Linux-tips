**Cron** é forma mais popular de agendar tarefas no Linux. Contudo, está não é a única opção disponível quando o assunto é automatizar tarefas no penguim.

Uma alternativa são os Timers do **Systemd**, que assim como **Cron** permitem a criação de tarefas agendadas para serem executadas periodicamente em determinados horários, datas ou intervalos.

Os Timers são arquivos do **Systemd** que controlam eventos. Assim, para cada arquivo `.timer`, existe um arquivo `.service` correspondente (por exemplo, `foo.timer` e `foo.service`).

Por isso, tudo começa com a criação desses arquivos no diretório `~/.config/systemd/user/`.

Exemplo de arquivo `.timers`:

```
[Unit]
Description=Run foo on boot

[Timer]
OnBootSec=5min

[Install]
WantedBy=timers.target
```

Exemplo de arquivo `.service`:

```
[Unit]
Description=Run my foo script

[Service]
Type=oneshot
ExecStart=/home/user/scripts/foo.sh
```
