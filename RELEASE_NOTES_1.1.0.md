# Netrunner Studio 1.1.0

## Novidades

- Migração de projetos do OBS Studio, com cenas e fontes dos canvases
  Horizontal e Vertical. Também reconhece configurações do Aitum Vertical e
  do perfil do OBS quando os arquivos estão disponíveis.
- Migração do Streamlabs Desktop por coleção local/exportada e pacote `.overlay`,
  preservando cenas, fontes compatíveis e arquivos de mídia incluídos no pacote.
- Orientação para reconectar widgets do Streamlabs após a migração. URLs de
  widgets contêm tokens privados e não são preservadas em algumas exportações.
- Ação **Recortar** no menu de contexto da fonte para iniciar o recorte direto
  no canvas sem depender do atalho com Alt.

## Observações

- A migração substitui o projeto atual depois de confirmar e cria um backup.
  Reinicie o Netrunner Studio para carregar as cenas e configurações importadas.
- Widgets podem exigir que você cole novamente o Widget URL nas Propriedades
  da fonte e entre de novo na conta Streamlabs.
- Uma janela transitória do canvas ainda pode aparecer brevemente durante
  algumas transições; o efeito está em acompanhamento.

## Dependências e licenças

O instalador inclui o runtime OBS Studio 32.2.2 e o Spout2 1.12.0, mantidos
nas versões fixas. Os avisos, licenças e referências aos códigos-fonte desses
componentes acompanham a instalação. O código próprio do Netrunner Studio
permanece no repositório privado.

## Download

Baixe `NetrunnerStudio-Setup-1.1.0.exe`. Também estão disponíveis o ZIP com
instalador e checksum (`NetrunnerStudio-1.1.0-Installer-Windows-x64.zip`) e o
arquivo SHA-256 (`NetrunnerStudio-1.1.0-Installer.sha256`).
