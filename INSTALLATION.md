# Instalação e configuração

Resumo dos passos utilizados no servidor.

## 1. Servidor

- Máquina Linux na rede local com IP estático
- Acesso SSH para administração

## 2. Instalação do pi-hole

```bash
curl -sSL https://install.pi-hole.net | bash
```

Durante a instalação foram definidos:

- IP estático do servidor
- DNS upstream utilizado
- Blocklist padrão de anúncios e rastreadores
- Senha de acesso ao painel administrativo

## 3. Configuração da rede

- DHCP do roteador apontando os clientes para o IP do servidor
- Alternativa: configuração manual do DNS em cada dispositivo

## 4. Verificação

- Painel web: `http://IP_DO_SERVIDOR/admin`
- Teste de bloqueio:

```bash
dig dominio-de-anuncio.example   # retorna 0.0.0.0 (bloqueado)
dig google.com                   # resolução normal
```

## 5. Manutenção

- Atualização das blocklists pelo painel
- `pihole -up` para atualizar o pi-hole
- `pihole -t` para consultas em tempo real
