# Painel LEEl VPN

Este painel é separado do APK Android. O APK continua a ser um aplicativo móvel Flutter/Android; o painel apenas cria documentos JSON que podem ser hospedados online.

## Criar configurações

Abra `index.html`, escolha o protocolo e preencha os campos. O construtor suporta SSH Proxy, SSH Direct, TLS, UDP, WebSocket, Shadowsocks, VLESS, VMess, WireGuard e DNS. Pode adicionar vários perfis, editar/remover perfis, preparar uma mensagem e definir URLs de subscrição.

Use **Descarregar config.json** e substitua o ficheiro `panel/config.json` pelo resultado. Use **Descarregar update.json** para atualizar a versão e o URL do APK.

## Publicar online

O workflow `.github/workflows/panel-pages.yml` publica a pasta `panel` através do GitHub Pages. Na primeira utilização, o proprietário do fork deve abrir **Settings → Pages**, escolher **GitHub Actions** como fonte e guardar. Depois de alterar os ficheiros, faça commit para `main`; o workflow publica os documentos no endereço do Pages do repositório.

O navegador não recebe token do GitHub. Isso evita expor credenciais administrativas. Para publicação por botão, seria necessário um backend OAuth separado; por enquanto a publicação é feita por commit no fork.

## Consumo pelo APK

A aplicação móvel pode importar as URLs de subscrição e atualizar os perfis remotos. Os objetos `profiles` gerados pelo painel mantêm o modo/protocolo e os campos específicos. Um servidor de subscrição pode converter estes objetos para o formato nativo final do protocolo antes de os entregar ao cliente.

`update.json` contém a versão, build code, URL do APK e notas. O APK LEEl VPN foi redirecionado para as releases do fork. Os releases Android devem continuar a ser gerados pelo GitHub Actions.
