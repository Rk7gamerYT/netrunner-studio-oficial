# Netrunner Studio A_0.4.8 Alpha

## Download

Baixe `NetrunnerStudio-A_0.4.8-Installer-Windows-x64.zip`, extraia o conteúdo
e execute `NetrunnerStudio-Alpha-Setup-0.4.8.exe`. O ZIP contém o instalador e
o arquivo SHA-256 para verificar a integridade.

## Novidades

- Saídas de live agrupadas por canvas, com configuração e início independentes
  para os canvases Principal e Vertical.
- Renomeação de cenas e fontes pelo menu de contexto ou com `F2`.
- Ícone do aplicativo com indicador roxo enquanto gravação ou transmissão
  estiver ativa.
- Mixer diferencia visualmente canais mutados com aparência monocromática.
- Polimento de consistência dos painéis e do gerenciamento de destinos.
- Mantém as melhorias A_0.4.7 nos comandos de fonte inspirados no OBS,
  transformações, atalhos, diálogos de transição e Modo Estúdio.

## Validação

A suíte Python passou com 122 testes aprovados e 56 ignorados por dependerem de
hardware, OBS local ou ambiente específico. Permanece um warning conhecido de
desconexão de sinal durante um teste de animação.

## Transparência

Esta é uma release alpha para testes. O instalador não tem assinatura
Authenticode reconhecida; o Windows pode exibir um aviso do SmartScreen.
Teste em uma cópia do projeto antes de usar em uma transmissão importante.

O código próprio permanece no repositório privado. A release pública contém
somente o instalador, o checksum e os avisos/licenças de terceiros.
