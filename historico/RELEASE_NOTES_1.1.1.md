# Netrunner Studio 1.1.1

Atualização de correção para quem teve problemas ao importar projetos e criar
ou aplicar perfis de configuração.

## Correções

- Importar projeto, OBS ou Streamlabs agora mantém o conteúdo separado até o
  próximo início. O autosave da sessão aberta não sobrescreve mais as cenas
  importadas.
- A migração do OBS e Streamlabs carrega junto as resoluções e configurações de
  áudio disponíveis antes de abrir o motor de vídeo.
- O rascunho antigo do Modo Estúdio é descartado ao ativar outro projeto.
- Perfis de configuração agora restauram os valores padrão quando uma opção
  não existe no perfil salvo.
- Salvar um perfil inclui os ajustes pendentes da janela de Configurações.
  Aplicar um perfil fecha a janela antiga para evitar que os controles
  desatualizados gravem por cima dele.
- Importar uma coleção de cenas como perfil agora mostra uma orientação clara
  para usar a seção Projeto.

## Dependências e licenças

O instalador inclui o runtime OBS Studio 32.2.2 e o Spout2 1.12.0. Seus avisos,
licenças e referências acompanham a instalação. O código próprio do Netrunner
Studio permanece no repositório privado.

## Downloads

- `NetrunnerStudio-Setup-1.1.1.exe`
- `NetrunnerStudio-1.1.1-Installer-Windows-x64.zip`
- `NetrunnerStudio-1.1.1-Installer.sha256`
