# WILKER Rotina Pessoal

Site estático em português para organizar a rotina de segunda a sexta. Funciona no GitHub Pages e não precisa de Node.js, instalação de dependências ou servidor próprio.

## Recursos

- Cronograma fixo de segunda a sexta, das 06:00 às 23:00.
- Alarmes sonoros e notificações do navegador no início de cada bloco.
- Soneca do alarme por 5 minutos e opção de dispensar o aviso.
- Marcação de tarefas concluídas por dia.
- Visão semanal e metas de faculdade, programação, radar de tecnologia, inglês, academia, violão e leitura.
- Relógio, indicação da próxima tarefa e progresso do dia.
- Salvamento automático no armazenamento local do navegador.
- Interface responsiva para desktop, tablet e celular.
- Recursos de PWA/cache para reabrir a interface mais rapidamente depois do primeiro acesso.

## Como publicar no GitHub Pages

1. Crie um repositório no GitHub, por exemplo `wilker-rotina`.
2. Extraia todos os arquivos desta pasta e envie **o conteúdo da pasta** para a raiz do repositório. O `index.html` precisa ficar na raiz.
3. No GitHub, abra **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**.
5. Selecione a branch `main` e a pasta `/ (root)`, depois clique em **Save**.
6. Aguarde a publicação do GitHub Pages e abra a URL exibida nessa tela.

## Como usar os alarmes

1. Abra o site publicado usando HTTPS (o endereço do GitHub Pages já usa HTTPS).
2. Clique em **Ativar alarmes** e permita as notificações se o navegador solicitar.
3. Mantenha o site aberto em uma aba do navegador. O som e os avisos são disparados no início de cada atividade de segunda a sexta.
4. Para testar, ative o alarme antes de um próximo horário de início programado. Os alarmes não tocam retroativamente para horários que já passaram.

**Limitação importante:** alarmes programados pelo JavaScript do navegador dependem da página estar aberta e de o computador não estar suspenso. Se fechar o navegador, o sistema operacional suspender o computador ou o navegador encerrar a aba, os alarmes podem não disparar. O cache/PWA ajuda a abrir o site offline depois de carregado, mas não cria um serviço de alarme em segundo plano quando o site está fechado.

## Salvamento dos dados

As marcações e preferências ficam salvas no `localStorage` do navegador e do dispositivo em que você abriu o site. Use o mesmo navegador/dispositivo para manter os dados. Limpar os dados do navegador pode apagar o progresso; as marcações não são sincronizadas automaticamente com outros dispositivos.

## Personalizar horários ou tarefas

Edite `TASKS` no arquivo `app.js`. Cada tarefa possui `id`, `start`, `end`, `title`, `category`, `tag` e `description`. Use horários no formato `HH:MM`. O alarme será disparado no valor de `start`.

## Arquivos

- `index.html`: estrutura do site.
- `styles.css`: aparência responsiva.
- `app.js`: cronograma, progresso, armazenamento e alarmes.
- `manifest.json`, `sw.js`, `favicon.svg`: recursos de instalação/cache e ícone.
