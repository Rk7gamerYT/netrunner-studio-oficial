# Histórico de versões

Resumo de cada versão publicada. As notas completas, os instaladores e os
hashes ficam na página de cada [Release](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases).

## 2.3 — interface renovada

- **[2.3.5](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.3.5):** fontes de página (navegador) sempre pela placa de vídeo; se o Chromium não conseguir usar a placa, a página é desligada com um aviso em vez de levar o processador a 100%; página que trava é recarregada sozinha; Vulkan Video desligado na RX 6600/6600M com o driver 32.0.21045.5002 (o AMF codifica); o teste de hardware não fecha mais com acento no caminho da Área de Trabalho; pacote de diagnóstico com o uso do processador por parte, os últimos 10 minutos e os travamentos da semana.
- **[2.3.4](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.3.4):** a live na Kick volta a funcionar com o novo formato (servidor e chave separados); prévia, live e gravação não congelam mais depois de minimizar o app e trocar de cena; uma captura que falha não derruba mais o vídeo; sem o aviso de cena inexistente ao trocar de cena; o MP4 automático ignora gravações vazias.
- **[2.3.3](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.3.3):** placas AMD (RX 6000, 7000 e 9000) passam a usar o AMF no modo automático; renomear cena atualiza a Prévia do Modo Estúdio; WebSocket não aceita mais senha vazia; prévias pausadas com a janela minimizada ou coberta; tema com o gradiente da marca e barra superior compacta.
- **[2.3.2](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.3.2):** menos uso de GPU na composição das cenas, NVENC sem leitura de volta pela CPU e fontes de navegador pela placa de vídeo; Multi-RTMP com outra faixa de áudio volta a ter som; atalhos com AltGr, teclado numérico e F13–F24; o WebView2 deixa de ser usado (só o Chromium embutido).
- **[2.3.1](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.3.1):** sem CPU alta quando um dispositivo de áudio salvo some; mais memória para muitas fontes de navegador em placas com pouca memória.
- **[2.3.0](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.3.0):** interface renovada (faders circulares, lista de fontes compacta), canvas em edição identificado, rodapé com CPU, GPU, FPS, quadros perdidos e bitrate medidos; janela que cabe em telas 720p/768p.

## 2.2 — Chromium nas fontes de navegador

- **[2.2.7](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.2.7):** a prévia do Modo Estúdio passa a aparecer.
- **[2.2.6](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.2.6):** prévia do Modo Estúdio sem resto da Central da Live.
- **[2.2.5](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.2.5):** painéis recolhidos voltam inteiros.
- **[2.2.4](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.2.4):** mudar o vídeo não falha mais com o canvas Vertical sem uso.
- **[2.2.3](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.2.3):** pacote de diagnóstico reformulado, com prévia antes de salvar e log em arquivo; o atualizador passa a encontrar a versão mais nova.
- **[2.2.2](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.2.2):** aplicar o vídeo não falha mais em placas integradas lentas.
- **[2.2.1](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.2.1):** correções do feedback dos testers (animação de opacidade, diagnóstico, importar perfil).
- **[2.2.0](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.2.0):** fontes de navegador no Chromium (CEF), com páginas abrindo em frações de segundo e o som da página no mixer.

## 2.1 — escolha de placa e atalhos

- **[2.1.1](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.1.1):** Modo Estúdio não trava mais o computador com muitas fontes de navegador; NVENC em drivers NVIDIA mais antigos.
- **[2.1.0](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.1.0):** escolha da placa de vídeo, teste de hardware na primeira abertura, NVENC H.264 (inclusive sem Vulkan Video), Quick Sync composto e atalhos de teclado completos.

## 2.0 — NetEngine no lugar do libobs

- **[2.0.2](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.0.2):** economia de GPU na prévia (30 FPS, capturas suspensas sem consumidor).
- **[2.0.1](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.0.1):** AMD AMF.
- **[2.0.0](https://github.com/Rk7gamerYT/netrunner-studio-oficial/releases/tag/v2.0.0):** o Studio passa a rodar sobre o NetEngine, o motor próprio em Vulkan. Sai o libobs, o runtime e os plugins do OBS; entra a codificação H.264 pelo processador para quem não tem codificador na placa.

## 1.x, betas e alfas (libobs)

As versões 1.0.0 a 1.2.1, as betas B_0.5.x e as alfas A_0.4.x usavam o runtime
do OBS Studio. Suas notas estão nas Releases e alguns documentos da época em
[historico/](historico/).
