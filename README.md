# Netrunner Studio 1.1.1

O Netrunner Studio é um estúdio de produção ao vivo para Windows, com
canvas horizontal 16:9 e vertical 9:16, Prévia/Programa, cenas, fontes,
mixer de áudio, transições e controles em um fluxo inspirado no OBS, com
identidade própria.

Esta é uma versão estável, depois de uma sequência de betas
(B_0.5.0 a B_0.5.7) publicadas e testadas por usuários reais. Este
repositório é o canal público de distribuição. O código próprio do
Netrunner Studio permanece fechado no repositório privado de
desenvolvimento; esta página e as Releases publicam somente os artefatos de
instalação e verificação, nunca os arquivos-fonte próprios.

## Download e instalação

Baixe direto o instalador na
[Release 1.1.1](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v1.1.1)
(`NetrunnerStudio-Setup-1.1.1.exe`) e siga estes passos:

1. Baixe `NetrunnerStudio-Setup-1.1.1.exe`.
2. Execute o instalador baixado.
3. Abra o Netrunner Studio pelo atalho criado no Menu Iniciar ou na área de
   trabalho.

O instalador é por usuário e não precisa de privilégios de administrador.
Nesta versão bundled, Python, OBS Studio e plugin Spout2 instalados
separadamente não são necessários para executar o app. Um ZIP com o
instalador + checksum (`NetrunnerStudio-1.1.1-Installer-Windows-x64.zip`)
continua disponível na mesma Release para quem preferir.

## Verificação do download

A Release publica `NetrunnerStudio-1.1.1-Installer.sha256` como arquivo
separado. Depois de baixar o instalador, no PowerShell execute:

```powershell
Get-FileHash .\NetrunnerStudio-Setup-1.1.1.exe -Algorithm SHA256
```

Compare o resultado com o hash publicado no arquivo `.sha256`. O instalador
não possui assinatura Authenticode reconhecida (sem certificado pago); o
Windows pode exibir um aviso do SmartScreen mesmo quando o hash está
correto.

## Novidades da 1.1.1

- Corrige importações de projetos e migrações OBS/Streamlabs que podiam ser
  sobrescritas pelo autosave da sessão anterior.
- Perfis agora restauram valores padrão e salvam os ajustes pendentes da janela
  de Configurações.
- A interface explica onde importar coleções de cenas e orienta aplicar e
  reiniciar depois de importar um perfil.

Consulte as [notas da 1.1.1](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v1.1.1).

## Novidades da 1.1.0

- Migração do OBS com cenas e fontes dos canvases Horizontal e Vertical,
  incluindo suporte às configurações do Aitum Vertical.
- Migração do Streamlabs Desktop por coleção e pacote `.overlay`, com fontes
  compatíveis e arquivos de mídia incluídos no pacote.
- Ação **Recortar** no menu de contexto da fonte para iniciar o recorte no canvas.
- Dica para reconectar widgets do Streamlabs sem expor o token privado.

Consulte as [notas da 1.1.0](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v1.1.0).

## Novidades da 1.0.5

- Mixer horizontal/vertical, com controles compactos e atalhos SVG.
- Menu de contexto do mixer, contador de ocultos e opções para fontes inativas.
- Propriedades de áudio avançadas: mono, balanço, sincronização, monitoramento e faixas.
- Sincronização de cenas vinculadas na Prévia do Modo Estúdio.
- Recorte direto no canvas com Alt + arrastar e bordas roxas para indicar o modo.
- Ajustes de inicialização, janelas transitórias e consistência visual.

Consulte as [notas da 1.0.5](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v1.0.5),
incluindo a limitação conhecida das janelas transitórias em algumas transições.

## Novidades da 1.0.4

- Faixa de áudio por plataforma no Multi-RTMP: cada saída de transmissão
  (Twitch, YouTube, Kick, etc.) agora escolhe qual das 6 faixas de áudio
  (Configurações → Áudio) ela recebe, permitindo mandar mixes diferentes
  pra plataformas diferentes ao mesmo tempo -- por exemplo, uma plataforma
  com o mix completo e outra sem o microfone, sem precisar de duas
  transmissões separadas.

## Novidades da 1.0.3

Leva de estabilidade interna, sem mudança visível de funcionalidade:

- Corrigido: uma condição de corrida rara podia perder uma alteração de
  configuração se duas escritas acontecessem quase ao mesmo tempo.
- Corrigido: fechar a tela de Configurações durante uma verificação de
  atualização em andamento podia travar o app.
- Corrigido: cancelar a escolha de janela/monitor/câmera/sender Spout2/
  cena ou fonte existente antes da resposta do motor chegar podia travar
  o app mais tarde, quando a resposta finalmente chegasse.
- Corrigido: uma animação de transformação/opacidade em andamento não
  trava mais o app se o motor nativo cair no meio dela.
- O download automático de atualização agora confere o hash SHA-256 que
  o próprio GitHub publica para o arquivo antes de aceitá-lo.

## Novidades da 1.0.2

- Atalhos do menu de contexto funcionam com foco na Prévia e nos outros
  painéis; comandos do canvas não dependem de uma fonte selecionada.
- O copiar e colar padrão dos campos de texto continua funcionando.
- Cada tipo de fonte reúne “Novo” e as fontes existentes daquele tipo no
  mesmo submenu, como no OBS.
- Spout2 1.12.0 vem incluído e fixado no instalador; não exige instalação
  separada do OBS Studio ou do plugin para usar fontes Spout.

## Novidades da 1.0.0

- Adicionado: "Perfis de Configuração" (Configurações → Geral) -- salve as
  configurações atuais (vídeo, encoder, áudio, atalhos, Modo Estúdio, Modo
  Clássico, rede...) como um perfil nomeado, troque entre perfis salvos,
  duplique/renomeie um perfil, e exporte/importe um perfil pra backup ou
  pra levar pra outra máquina.
- Adicionado: módulo de Atualização (Configurações → Geral + barra de
  status) -- verifica novas versões publicadas, com aviso automático ao
  abrir o app. Nunca baixa ou instala nada sozinho: só aponta pro navegador
  ou baixa o ZIP como um arquivo comum, a instalação continua manual.
- Adicionado: cor e ícone personalizado por cena (Cenas → botão direito) --
  paleta de 8 cores (ou personalizada) e 12 ícones, viaja junto com
  "Exportar/Importar projeto".
- Adicionado: busca ao vivo em Configurações, grupos recolhíveis, selos de
  "Aplicação imediata"/"Requer reinício" em cada opção, e "Restaurar
  padrões" (por seção ou geral).
- Adicionado: densidade de interface (compacto/padrão/confortável, sem
  precisar reiniciar) e layouts de dock nomeados (salvar/aplicar/excluir
  a disposição dos painéis).
- Adicionado: contador de tempo decorrido nos botões de gravação e
  transmissão, splitter redimensionável entre as prévias, modo de zoom
  "Preencher", projetor em tela cheia, e docks de Estatísticas e Logs.
- Adicionado: detecção de clipping e reset de fader por duplo clique no
  mixer de áudio; busca nas Fontes.
- Corrigido: o menu "Pré-visualização" agora mostra "Ativar"/"Desativar" (e
  "Bloquear"/"Desbloquear") de acordo com o estado real do canvas; 12
  atalhos de teclado do painel de Fontes que mostravam a tecla no menu mas
  não funcionavam de verdade (Transformar, Projetar, Capturar, Mover);
  botões do painel de Controles que podiam encolher até sumir num dock
  estreito.

## Recursos

- Adicionado: placeholder de "Pré-visualização desativada" com a identidade
  visual do próprio Netrunner Studio (em vez da tela cinza genérica do OBS)
  ao desativar a prévia de um canvas.
- Adicionado: "Modo Clássico" (Configurações → Geral) -- oculta o canvas
  Vertical na tela de Cenários pra quem quer trabalhar só com o Horizontal,
  como o OBS tradicional. Requer reiniciar o app para aplicar.
- Corrigido: removida a dica "Ctrl+Z desfaz..." que aparecia toda vez que o
  mouse passava sobre a prévia.
- Adicionado: "Filtro de redução" (Configurações → Vídeo, ambos os
  canvases) e o filtro de escala por item de cena agora oferecem 3 níveis
  de FSR -- "FSR Balanceado", "FSR Qualidade" e "FSR Desempenho".
- Adicionado: suporte a AMD FidelityFX Super Resolution (FSR) para melhorar
  a nitidez de fontes redimensionadas -- filtros "Redimensionar FSR" e
  "Nitidez FSR" (Filtros → Adicionar).
- Corrigido (segurança): a senha do WebSocket ficava descriptografada na
  memória durante toda a sessão da tela de Configurações, mesmo sem clicar em
  "Mostrar".
- Corrigido: o Modo Estúdio não sincronizava com a Prévia uma fonte
  adicionada/removida numa cena já enviada ao vivo antes.
- Adicionado: arrastar cenas com o mouse para reorganizá-las.
- Corrigido: "Cenas Vinculadas" não funcionava corretamente durante o Modo
  Estúdio.
- Corrigido: "Cenas Vinculadas" não sobrevivia a um reinício do app.
- Ícone próprio na barra de tarefas enquanto grava ou transmite, no lugar do
  antigo selo roxo por cima do ícone normal.
- Suporte a gravação em MP4, MOV, FLV e MPEG-TS (além de MKV) e a codecs de
  áudio Opus, FLAC e PCM (além de AAC), com aviso explícito de que MP4/MOV
  não são tão resistentes a uma queda do app quanto o MKV.
- Pausar e retomar a gravação sem finalizar o arquivo, sem afetar uma
  transmissão simultânea do mesmo canvas.
- Faixas de áudio da gravação movidas para Configurações → Áudio.
- Correções de bugs reais reportados por usuários: exibição de dispositivo de
  áudio em Configurações, persistência das opções avançadas do Modo Estúdio e
  perda de filtros de áudio ao reselecionar um dispositivo.

- Modo Estúdio com Prévia e Programa independentes.
- Canvas horizontal e vertical sincronizados quando o destino conjunto está
  habilitado.
- Publicação com ciclo real de transição, incluindo Corte, Fade, Swipe e
  Slide, com bloqueio do botão até a conclusão.
- Cenas e fontes com salvamento automático após alterações confirmadas.
- `Ctrl+Z` para desfazer alterações estruturais e transformações do canvas.
- Mixer de áudio, controles de transmissão/gravação e composição isolada na
  Prévia.
- Runtime necessário do OBS Studio bundled nesta build, com os avisos e
  licenças correspondentes dentro da instalação.
- Correção do crash de fechamento durante transições do Modo Estúdio.
- Persistência de projeto e rascunho da Prévia validada após reinicialização.
- Cobertura permanente para WebSocket, efeitos, animações, gravação,
  Multi-RTMP e Cenas Vinculadas.
- Revisões pontuais de performance no motor nativo e na interface.
- Menu de contexto de fontes organizado por categorias, com comandos de
  composição, transformação, pré-visualização e atalhos inspirados no OBS.
- Diálogos de propriedades de transição redesenhados, com prévia A/B compacta,
  campos alinhados e seletor de cor mais claro.
- Destinos de transmissão configuráveis separadamente por canvas, incluindo
  o canvas Vertical.
- Renomeação de cenas e fontes com `F2` ou pelo menu do botão direito.
- Indicador roxo no ícone do app durante gravação ou transmissão ao vivo.
- Canais mutados do mixer apresentados em escala de cinza para distinção rápida.
- Correções de persistência e de consistência visual nos painéis de transmissão.
- Ícones SVG padronizados e cards de destinos com gradiente compartilhado,
  alinhamento consistente e suporte ao Kick, Trovo, Facebook e X.
- Captura de monitor usando DXGI por padrão, com restauração validada após
  reinício enquanto a captura estava ativa.

## Avisos

Esta é uma versão estável, mas ainda sem assinatura de código
(certificado de assinatura não é viável no momento -- ver Licenças). Podem
existir bugs, incompatibilidades com hardware específico ou avisos do
antivírus/SmartScreen. Para reportar um problema, informe a versão do
Windows, GPU, passo a passo para reproduzir, transição/canvas usados e, se
possível, o horário do teste e uma captura.

Não substitua os arquivos instalados manualmente. Para testar uma versão nova,
instale o pacote correspondente pela Release; o instalador mantém a
instalação por usuário em `%LOCALAPPDATA%\Netrunner Studio`.

## Licenças

O código próprio, a marca e os recursos do Netrunner Studio não são publicados
neste repositório. A build bundled inclui o runtime OBS Studio e o plugin Spout2 sob GPLv2, com licenças, avisos de terceiros e referências aos códigos-fonte correspondentes dentro da instalação.
