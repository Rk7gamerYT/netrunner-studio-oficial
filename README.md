# Netrunner Studio

O Netrunner Studio é um estúdio de produção ao vivo para Windows, com canvas
horizontal 16:9 e vertical 9:16, Prévia/Programa (Modo Estúdio), cenas, fontes,
mixer de áudio, transições, gravação e transmissão para várias plataformas ao
mesmo tempo, num fluxo inspirado no OBS e com identidade própria.

Desde a versão 2.0 o Studio roda sobre o **NetEngine**, o motor próprio do
Netrunner (Vulkan): o aplicativo não usa mais o libobs nem o runtime do OBS.

Este repositório é o **canal público de distribuição**. O código do Netrunner
Studio e do NetEngine é fechado e fica nos repositórios privados de
desenvolvimento; aqui ficam só os instaladores (nas
[Releases](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases)),
os avisos de licença e as notas de cada versão.

**Versão atual: 2.3.3.** Site oficial: <https://netrunnerstream.com.br/studio>.

## Download e instalação

Baixe o instalador na
[última Release](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/latest).
Cada versão publica três arquivos:

| Arquivo | Para quê |
| --- | --- |
| `NetrunnerStudio-Setup-X.Y.Z.exe` | O instalador. É o que a maioria das pessoas deve baixar. |
| `NetrunnerStudio-X.Y.Z-Installer-Windows-x64.zip` | O mesmo instalador num ZIP, com o selo de build. É o arquivo que o atualizador do app baixa. |
| `NetrunnerStudio-X.Y.Z-Installer.sha256` | O hash SHA-256 do instalador, para conferir o download. |

1. Baixe `NetrunnerStudio-Setup-X.Y.Z.exe`.
2. Execute o instalador. Ele é por usuário e não pede administrador.
3. Abra o **Netrunner Studio NetEngine** pelo Menu Iniciar ou pelo atalho da
   área de trabalho.

Na primeira abertura o Studio testa cada placa de vídeo do computador, uma de
cada vez, e recomenda a melhor e o codificador para ela. Nada é capturado nem
enviado.

### Onde ficam os arquivos

- Programa: `%LOCALAPPDATA%\Programs\Netrunner Studio NetEngine`.
- Configurações, perfis e projetos: `%APPDATA%\NetrunnerNext`. A instalação, a
  atualização e a desinstalação não apagam essa pasta.
- As versões 1.x (baseadas no libobs) usavam outra pasta e outra identidade de
  instalador. A 2.x se instala ao lado delas, sem sobrescrever; não copie
  arquivos de uma instalação para a outra.

### Atualizações

O Studio avisa quando sai uma versão nova (Configurações → Geral e barra de
status). O atualizador baixa o ZIP da Release, confere o hash SHA-256 que o
GitHub publica e o selo de build, e só então abre o instalador. Você também pode
baixar e instalar por cima a qualquer momento, sem perder as configurações.

## Requisitos

- Windows 10 (1809 ou mais recente) ou Windows 11, 64 bits.
- Placa de vídeo com **Vulkan** e driver atualizado (NVIDIA, AMD ou Intel).
- Codificação de vídeo por hardware quando disponível: NVENC (NVIDIA, inclusive
  placas sem Vulkan Video), AMD AMF, Intel Quick Sync e Vulkan Video. Sem
  codificador na placa, o Studio usa o codificador H.264 do próprio Windows no
  processador.
- Python, OBS Studio e plugins do OBS **não** são necessários.

## Verificação do download

O instalador não tem assinatura de código paga, então o Windows pode mostrar o
aviso do SmartScreen mesmo com o arquivo correto. Para conferir, compare o hash
do arquivo baixado com o do `.sha256` da mesma Release. No PowerShell:

```powershell
Get-FileHash .\NetrunnerStudio-Setup-X.Y.Z.exe -Algorithm SHA256
```

Só instale se o resultado for igual ao publicado. O GitHub também mostra o
SHA-256 de cada arquivo na página da Release.

## Novidades da 2.3.3

- **Placas AMD (Radeon RX 6000, 7000 e 9000):** o modo automático escolhe o AMF
  antes do Vulkan Video, e quem tinha ficado preso no Vulkan Video volta para
  "Automático" na primeira abertura.
- **Modo Estúdio:** renomear uma cena atualiza também a Prévia.
- **WebSocket:** com a senha ligada e ainda vazia, o servidor não aceita mais
  senha vazia; uma senha é gerada ao salvar.
- **Prévias pausadas** com a janela minimizada ou coberta, economizando GPU.
- **Visual novo:** o gradiente da marca como único destaque, barra superior
  compacta com seletor de canvas e estado ao vivo, e textos que cabem a 1280x720.

O histórico de todas as versões está no [CHANGELOG](CHANGELOG.md), e as notas
completas de cada uma, na [página de Releases](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases).

## Recursos principais

- **Dois canvases:** Horizontal e Vertical lado a lado, com destinos de
  transmissão separados por canvas (ou o Modo Clássico, só com o Horizontal).
- **Modo Estúdio** com Prévia e Programa independentes e Cenas Vinculadas.
- **Fontes:** monitor (DXGI ou Windows Graphics Capture), janela e jogo sem
  injetar código, áudio por aplicativo, câmera, navegador (Chromium embutido,
  com o som da página no mixer), texto, imagem, GIF, mídia local e por endereço,
  Spout, cor, cena como fonte e grupos.
- **Filtros** de vídeo e de áudio, incluindo chroma key, LUT, FSR, shader
  personalizado, supressão de ruído RNNoise, compressor, limitador e sidechain.
- **Transições:** corte, esmaecer, swipe, slide, push, reveal, Stinger e Luma
  Wipe, por cena e por item.
- **Gravação** em MP4, MOV e MKV, com pausa, replay buffer, remux e os dois
  canvases ao mesmo tempo.
- **Transmissão** por RTMP, RTMPS, SRT e RIST para vários destinos ao mesmo
  tempo, cada um com sua faixa de áudio, com reconexão e bitrate dinâmico.
- **Central da Live:** login e chat da Twitch, Kick, YouTube (chat público) e
  TikTok (pelo plugin opcional abaixo).
- **Atalhos de teclado** globais, por cena e por fonte; **API WebSocket** para
  Stream Deck e Companion; migração de cenas do OBS e do Streamlabs.
- **Diagnóstico:** teste de hardware no Menu Iniciar ("Teste de hardware
  (Netrunner)") e pacote de diagnóstico em Configurações → Avançado.

## Plugin opcional: Netrunner TikTok Chat

O chat do TikTok é um programa separado e de código aberto (AGPL-3.0), que não
vem no instalador do Studio. Ele tem a própria Release:
[tiktok-chat-v1.0.0](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/tiktok-chat-v1.0.0).
O TikTok não tem API oficial de chat, então o plugin pode parar de funcionar
quando a plataforma mudar.

## Limitações conhecidas

- Jogos em **tela cheia exclusiva** não são capturados; use janela ou tela
  cheia sem borda.
- HDR e 10 bits ainda não são suportados; HEVC só pelo NVENC.
- Funções do YouTube que exigem entrar na conta aguardam a aprovação do Google;
  o chat público por @ funciona.

## Reportar um problema

Abra uma [issue](https://github.com/Rk7gamerYT/netrunner-studio-oficial/issues)
com a versão do Studio, a versão do Windows, a placa de vídeo, o passo a passo
para reproduzir e, se possível, o pacote de diagnóstico (Configurações →
Avançado → Diagnóstico) ou a pasta `netengine_diagnostico` que o "Teste de
hardware" cria na área de trabalho. Remova chaves de transmissão, tokens e
senhas antes de enviar.

Vulnerabilidades de segurança **não** vão em issue pública: veja
[SECURITY.md](SECURITY.md).

## Licenças

O código, a marca e os recursos do Netrunner Studio e do NetEngine são
proprietários ([LICENSE-NETRUNNER.txt](LICENSE-NETRUNNER.txt)) e não são
publicados neste repositório. O pacote inclui componentes de terceiros que
mantêm as próprias licenças, entre eles o Qt for Python (PySide6) e o FFmpeg
sob a LGPL-3.0, ligados dinamicamente e substituíveis, e o Chromium (CEF) das
fontes de navegador. A lista completa está em
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md), e os textos de licença vão
dentro da instalação.

Este repositório guarda também documentos das versões alfa e 1.x, baseadas no
libobs, em [historico/](historico/).
