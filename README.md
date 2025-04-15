# Tutorial: Configurando Squid com Controle por Arquivos Externos

Este repositório demonstra como configurar o Squid em um servidor Linux com regras de controle de acesso baseadas em arquivos externos.

## Requisitos

- Squid instalado (testado em Ubuntu/Debian)
- Acesso root para editar `/etc/squid/`

## Estrutura dos Arquivos

- `squid.conf`: arquivo de configuração principal
- `ip_liberados.txt`: lista de IPs permitidos
- `sites_liberados.txt`: lista de sites permitidos
- `sites_bloqueados.txt`: lista de sites bloqueados

## Passo a Passo

### 1. Instale o Squid

```bash
sudo apt update
sudo apt install squid -y
```

### 2. Copie os arquivos de configuração

```bash
sudo cp config/squid.conf /etc/squid/squid.conf
sudo cp config/ip_liberados.txt /etc/squid/
sudo cp config/sites_liberados.txt /etc/squid/
sudo cp config/sites_bloqueados.txt /etc/squid/
```

### 3. Reinicie o serviço

```bash
sudo systemctl restart squid
```

## Resultado

- Sites como `facebook.com` serão bloqueados
- Apenas os IPs e sites listados nos arquivos poderão navegar

---

Filipe Bianque – Coordenador de TI | São Francisco Hospital e Maternidade
