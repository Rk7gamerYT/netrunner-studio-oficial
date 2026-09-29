# Netrunner Studio 1.0.5

## Novidades

- Mixer com layouts horizontal e vertical. O modo vertical reúne fader,
  medidor, botões compactos empilhados, nível em dB e atalhos SVG para
  propriedades, filtros e faixas. A escolha do layout fica salva.
- Menu do botão direito no mixer com fixar, ocultar, travar volume,
  copiar/colar filtros, renomear e acesso às propriedades da fonte.
- Rodapé do mixer com contador de canais ocultos e menu Opções para exibir
  fontes ocultas/inativas e abrir as propriedades de áudio avançadas.
- Propriedades de áudio avançadas com volume, mono, balanço, atraso de
  sincronização, monitoramento e roteamento para as seis faixas.

## Correções e ajustes

- Cenas vinculadas também sincronizam a Prévia do Modo Estúdio, preservando
  as cenas que estão no Programa até enviar a transição.
- Recorte direto no canvas: selecione a fonte e arraste uma borda segurando
  Alt. A borda roxa indica o recorte; Ctrl+Z desfaz a alteração.
- Corrigido o preenchimento invertido do fader vertical e refinado o espaço
  dos controles, menus e tabela de áudio avançado.
- Mais ícones SVG nos menus de cenas, fontes, filtros e painéis.
- Ajustes na inicialização e na troca de Modo Estúdio para reduzir a aparição
  de janelas transitórias do canvas; inicialização do motor antecipada.

## Limitação conhecida

Uma janela transitória do canvas ainda pode aparecer brevemente durante
algumas transições. O efeito foi reduzido, mas a correção completa segue em
acompanhamento.

## Dependências e licenças

O instalador inclui o runtime OBS Studio 32.2.2 e o Spout2 1.12.0, mantidos
nas versões fixas. Os avisos, licenças e referências aos códigos-fonte desses
componentes acompanham a instalação. O código próprio do Netrunner Studio
permanece no repositório privado.

## Download

Baixe `NetrunnerStudio-Setup-1.0.5.exe`. Também estão disponíveis o ZIP com
instalador e checksum (`NetrunnerStudio-1.0.5-Installer-Windows-x64.zip`) e o
arquivo SHA-256 (`NetrunnerStudio-1.0.5-Installer.sha256`).
