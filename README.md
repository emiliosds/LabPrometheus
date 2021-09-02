# LabPrometheus

## Criando nomes amigáveis para seus servidores

```

- job_name: 'win-exporter'
  static_configs:
  - targets:
    - '127.0.0.1:1234@MEU-SERVIDOR'

  relabel_configs:
  - source_labels: [ __address__ ]
    regex: '.*@(.*)'
    replacement: $1
    target_label: instance
  - source_labels: [ __address__ ]
    regex: '(.*)@.*'
    replacement: $1
    target_label: __address__

```
