# Painel LEEl VPN

Este painel é separado do APK Android. O APK continua a ser um aplicativo móvel Flutter/Android; o painel apenas publica ficheiros estáticos.

## Configurações

Use `config.json` para guardar URLs de subscrições compatíveis com Sing-box, V2Ray ou Clash. O Hiddify/LEEl VPN já inclui atualização automática de perfis remotos; o utilizador adiciona a URL na app e o perfil é atualizado pelo próprio cliente.

## Mensagens

O campo `message` é o canal de mensagem preparado para o painel. Para aparecer dentro da app como aviso nativo, é necessário ligar este JSON a um provider Flutter específico; nesta primeira base ele é publicado para consumo do painel e futura integração, não é apresentado automaticamente pelo cliente upstream.

## Atualizações

`update.json` aponta para o último release do fork. O mecanismo de atualização do aplicativo foi redirecionado para as releases GitHub do fork LEEl VPN. Os APKs públicos devem ser produzidos pelo GitHub Actions, conforme a licença do Hiddify.
