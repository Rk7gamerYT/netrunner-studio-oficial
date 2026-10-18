# Netrunner Studio A_0.4.8 — checklist de release alpha

## O que já está pronto

- Captura de jogo com limite de FPS habilitado por padrão, cursor oculto por
  padrão e configuração explícita do hook para evitar impacto no frametime.
- Captura de monitor usando o caminho oficial WGC/DXGI, sem a rota GDI de
  compatibilidade, com validação de GPU compatível com DirectX 10.1+.
- Encoders legados removidos; a seleção segue os encoders modernos documentados
  para o runtime atual do OBS.

- Nuitka em modo `standalone`: o usuário final não precisa ter Python
  instalado.
- PySide6/Qt fixado em `6.10.1` e compilado sem UPX, evitando a falha de
  carregamento do `Qt6Core.dll` reproduzida nas builds anteriores.
- Metadados de versão e produto no executável.
- Inno Setup por usuário, sem exigir administrador.
- Layout dos painéis versionado: instalações antigas não restauram geometrias
  obsoletas ou sobrepostas.
- Avisos de terceiros separados do código proprietário.
- Seleção de fontes pela lista sincronizada com o preview, permitindo editar
  itens sobrepostos.
- Submenu OBS “Transformar” para fontes, com editar, copiar/colar, limpar,
  girar, inverter, ajustar/estender/centralizar à tela e atalho `Ctrl+F`.
- Menu de contexto de fontes reorganizado por categorias, preservando os
  comandos OBS e seus atalhos sem ultrapassar a altura da tela.
- Propriedades de transição com prévia A/B legível, formulário em cartão,
  seletor de cor explícito e altura adaptada ao tipo de transição.
- Reordenação de fontes por arrastar e soltar.
- Estado do botão de transmissão atualizado imediatamente após iniciar/parar.
- Menus, filtros e estados selecionados harmonizados com a paleta do Overlay
  Engine e ícones SVG padronizados.
- Crash de fechamento durante transições do Modo Estúdio corrigido e coberto
  por teste de regressão nativo.
- Persistência de projeto, rascunho da Prévia, filtros e mixer validada após
  fechar e reabrir um processo novo.
- API WebSocket, efeitos, animações, gravação, Multi-RTMP e Cenas Vinculadas
  cobertos por testes permanentes.
- Revisões pontuais de performance no motor nativo e na interface Python/Qt.
- Saídas de transmissão organizadas por canvas, com suporte próprio para
  destinos do canvas Vertical e sem fluxo duplicado de adição de destinos.
- Estado do mixer em mute claramente indicado com tratamento monocromático.
- Indicador roxo no ícone do aplicativo enquanto houver gravação ou live ativa.
- Renomeação de cenas e fontes pelo menu de contexto ou pela tecla `F2`.
- Ajustes de consistência visual nos painéis e na lista de saídas.

## Gates antes de publicar

1. Manter PySide6 na opção LGPL e revisar os avisos de terceiros antes de
   publicar.
2. Definir o endereço/repositório oficial onde o código-fonte do OBS e os
   avisos serão disponibilizados.
3. Assinar o instalador e o executável principal quando houver certificado de
   assinatura de código. Sem dinheiro para certificado, publicar HTTPS,
   SHA-256 e os avisos é a alternativa honesta, mas não elimina o SmartScreen.
4. Testar em uma máquina limpa, sem Python, PyQt ou OBS pré-instalados quando
   a variante bundled for escolhida.
5. Submeter os hashes e o instalador aos portais de reputação do antivírus,
   quando disponíveis.

Assinatura digital reduz alertas de reputação, mas não garante que nenhum
antivírus fará uma detecção. Certificado autoassinado não resolve o problema
para usuários finais.
