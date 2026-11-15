# Plano — Painel LEEl VPN

## Objetivo

Expandir o painel web separado do APK para criar e publicar configurações remotas, mensagens e metadata de atualização. O aplicativo continua móvel Android/Flutter e usa perfis/subscrições remotos.

## Implementação

- `panel/index.html`: interface responsiva com formulário por protocolo, lista editável de perfis, mensagem, URLs de subscrição e metadata do APK.
- `panel/config.json`: documento publicado pelo GitHub Pages com `profiles`, `subscriptionUrls`, `message` e `updatedAt`.
- `panel/update.json`: metadata de versão e URL do APK publicado no GitHub Release.
- GitHub Pages continua a servir o painel e os documentos estáticos.
- O utilizador exporta os JSON e publica-os no fork; não se coloca token do GitHub no navegador.

## Protocolos do construtor

SSH Proxy, SSH Direct, TLS, UDP, WebSocket, Shadowsocks, VLESS, VMess, WireGuard e DNS. O painel guarda o modo e os campos específicos num formato JSON estável, permitindo que o adaptador da aplicação ou o servidor de subscrição converta os perfis para o formato final suportado.

## Design

- Estilo escolhido: dashboard técnico escuro com superfícies azul-marinho e acentos azul-violeta.
- Princípios: legibilidade operacional, campos contextuais por protocolo, feedback imediato e exportação segura.
- Movimento: sem animações decorativas; transições curtas apenas para estados de formulário.
- Voz: direta e técnica, com ações como “Adicionar configuração” e “Publicar ficheiros”.
- Marca: LEEl VPN é apresentado como ferramenta de gestão de perfis móveis, não como aplicação web.
