# Netrunner Studio — avisos de terceiros

Este arquivo separa o código proprietário do Netrunner Studio (e do NetEngine) das bibliotecas
usadas pelo produto. Os textos de licença incluídos no instalador são válidos
somente para os componentes correspondentes.

## PySide6 / Qt for Python

- `PySide6`, `PySide6_Essentials`, `PySide6_Addons` e `shiboken6`: LGPL-3.0-only
  OR GPL-2.0-only OR GPL-3.0-only, conforme a opção escolhida na distribuição.
- O Netrunner usa a opção LGPL do PySide6; o código próprio continua separado e
  não é incorporado estaticamente ao Qt.
- Projeto: <https://wiki.qt.io/Qt_for_Python>
- Licença: <https://www.gnu.org/licenses/lgpl-3.0.html>

A camada Qt foi migrada de PyQt6 para PySide6 para evitar a dependência de uma
licença comercial. A distribuição ainda deve acompanhar este aviso e respeitar
as obrigações da LGPL, incluindo preservar os textos de licença e não impedir
que o usuário substitua as bibliotecas LGPL por versões compatíveis.

## psutil

- Licença: BSD-3-Clause.
- Projeto: <https://github.com/giampaolo/psutil>

## pytchat 0.5.5

- Licença: MIT.
- Projeto: <https://github.com/taizan-hokuto/pytchat>.
- O texto completo acompanha a aplicação em `assets/licenses/pytchat-LICENSE.txt`.
- As dependências HTTP/2 `h2`, `hpack` e `hyperframe` usam licença MIT; seus
  textos estão em `assets/licenses/h2-LICENSE.txt`, `hpack-LICENSE.txt` e
  `hyperframe-LICENSE.txt`.
- O adaptador de leitura do YouTube foi reaproveitado do Netrunner Overlay
  Engine. Usa um protocolo público não oficial e não encaminha credenciais
  OAuth nem chaves RTMP ao coletor. Envio e moderação continuam pela API oficial.
- A biblioteca está arquivada e o transporte pode deixar de funcionar quando
  o YouTube mudar seus endpoints internos. Esta licença não concede autorização
  do YouTube para scraping nem assegura aprovação em auditorias da plataforma.

## FFmpeg 9.0 (build LGPL de BtbN/FFmpeg-Builds)

- Licença: **GNU LGPL v3**. O build é o `lgpl-shared` (compilado **sem** `--enable-gpl` e sem `--enable-nonfree`; sem libx264/libx265), com as bibliotecas ligadas dinamicamente (`avcodec`, `avformat`, `avutil`, `avfilter`, `swscale`, `swresample` e `avdevice`, em DLLs). O texto completo acompanha o pacote em `netengine\FFmpeg-LICENSE.txt` e a versão exata em `netengine\FFmpeg-BUILD.txt`.
- Uso: `ffmpeg.exe` e `ffprobe.exe` ficam em `netengine\` ao lado do `netengine_host.exe` e são executados como processos separados (decodificação do Stinger com transparência, incluindo WebM com alfa via libvpx). O código do Netrunner Studio e do NetEngine não é ligado às bibliotecas do FFmpeg.
- As DLLs do FFmpeg em `netengine\` podem ser substituídas por outra versão compatível com a mesma API.
- Projeto: <https://ffmpeg.org/>
- Código-fonte correspondente: <https://git.ffmpeg.org/ffmpeg.git> (commit `46d8f462ee`, série n9.0) e os scripts de build com as bibliotecas de terceiros: <https://github.com/BtbN/FFmpeg-Builds>. Quem receber o pacote também pode pedir o código-fonte correspondente em até três anos pelos canais de suporte do Netrunner Studio.

## Netrunner TikTok Chat (plugin opcional, programa separado)

- Programa **separado, opcional e de código aberto** (AGPL-3.0-or-later) mantido pelo mesmo autor, que o usuário instala por conta própria; **não faz parte** do instalador do Netrunner Studio. Código-fonte completo: `plugins/tiktok-chat` (publicado em repositório público) e dentro do próprio pacote do plugin (`source\`).
- Usa o cliente não oficial [TikTokLive](https://github.com/isaackogan/TikTokLive) 7.0.0 (AGPL-3.0) e depende do serviço externo de assinatura Euler Stream.
- O Studio nunca importa nem copia esse código: só inicia o programa como processo filho e troca linhas JSON com ele (`app/tiktok_live_chat.py`).
- O chat do TikTok não tem API oficial; o uso desse protocolo pode contrariar os Termos do TikTok.

## Nuitka

- Compilador usado para gerar o executável do Netrunner Studio (traduz o Python em C e compila para código nativo). Licença do compilador: GNU AGPL v3; o programa gerado não passa a ser AGPL, e o Nuitka não transforma bibliotecas de terceiros em código proprietário do Netrunner Studio.
- Projeto: <https://github.com/Nuitka/Nuitka>

## PyInstaller

- Usado apenas para empacotar o plugin opcional do chat do TikTok (GPL v2 com exceção que permite distribuir o aplicativo empacotado sob outra licença).
- Projeto: <https://pyinstaller.org/>

## Inno Setup

- O instalador é gerado pelo Inno Setup; os termos do Inno Setup se aplicam ao
  compilador e à distribuição do instalador.
- Projeto: <https://jrsoftware.org/isinfo.php>

## AMD FidelityFX Super Resolution 1.0 (FSR1)

- Licença: MIT.
- Projeto: <https://github.com/GPUOpen-Effects/FidelityFX-FSR>
- Copyright (c) 2021 Advanced Micro Devices, Inc.
- O algoritmo EASU/RCAS de `ffx_fsr1.h` foi adaptado (não vendorizado como arquivo-fonte original) no filtro de escala e nitidez FSR do NetEngine (`netengine_host.exe`), sem shader de computação nem Gather4 e com recíprocas exatas no lugar das aproximações por bit-trick do original.

## Componentes do NetEngine (motor)

O motor (`netengine_host.exe`, `netengine_presenter.dll` e `netengine_diagnose.exe`) é
proprietário e usa estes componentes de terceiros. Os textos completos vão na
instalação em `THIRD_PARTY_NOTICES_NETENGINE.md` e `licenses\netengine\`.

- **Chromium Embedded Framework (CEF) e Chromium** — fontes de navegador. O CEF é
  BSD-3-Clause; o Chromium reúne componentes com várias licenças, listadas no
  `CREDITS.html` que acompanha o pacote. Vão no pacote `libcef.dll`,
  `netengine_cef_helper.exe`, o SwiftShader (`vk_swiftshader.dll`, Apache-2.0) e os recursos do
  Chromium. Projeto: <https://github.com/chromiumembedded/cef>.
- **AMD Advanced Media Framework (AMF)** — MIT. Codificação em placas AMD; o
  runtime vem do driver da AMD. A licença avisa que não concede licença de
  patentes de codecs (H.264, HEVC, AAC, MP3).
- **Intel oneVPL (libvpl)** — MIT. Codificação Intel Quick Sync.
- **FFmpeg nv-codec-headers** — MIT. Cabeçalhos da API do NVENC; o
  `nvEncodeAPI64.dll` vem do driver da NVIDIA.
- **RNNoise 0.2** — BSD-3-Clause. Filtro de supressão de ruído.
- **Spout2 SDK** — BSD-2-Clause. Fontes e saídas Spout.
- **AMD FidelityFX Super Resolution 1.0** — MIT (ver a seção acima).

O NetEngine não inclui código do libobs nem do OBS Studio.

## Regra de empacotamento

O pacote público (inclusive o `netengine\` com FFmpeg) deve manter estes avisos, os textos de licença aplicáveis e
os links de código-fonte correspondentes. Nenhum arquivo de terceiro deve ser
apresentado como código proprietário do Netrunner Studio.
