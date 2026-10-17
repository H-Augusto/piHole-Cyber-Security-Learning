# piHole — Servidor DNS com bloqueio de anúncios

Projeto de infraestrutura e redes: criei um **servidor Linux** e configurei o **pi-hole** como DNS da rede local, bloqueando anúncios e rastreadores no nível de DNS para todos os dispositivos conectados.

## O que foi feito

- Servidor Linux criado e configurado
- pi-hole instalado e configurado como servidor DNS local
- Dispositivos da rede usando o pi-hole como DNS
- Blocklists de anúncios e rastreadores ativas
- Painel administrativo para monitoramento das consultas

## Como funciona

```
Dispositivos da rede (PC, celular, IoT)
              │  consulta DNS
              ▼
   ┌──────────────────────────┐
   │  Servidor Linux          │
   │   └── pi-hole            │───▶ DNS upstream (internet)
   │       ├─ blocklist       │
   │       └─ dashboard/logs  │
   └──────────────────────────┘
```

1. Um dispositivo da rede faz uma consulta DNS
2. O pi-hole compara o domínio com as blocklists
3. Se for anúncio ou rastreador → a consulta é bloqueada
4. Caso contrário → encaminha para o DNS upstream e registra no log

## Recursos

- **Sistema:** Linux
- **Software:** pi-hole (DNS sinkhole)
- **Protocolos:** DNS e DHCP
- **Interface:** dashboard web com estatísticas e logs

## Instalação e configuração

Veja [INSTALLATION.md](INSTALLATION.md).
