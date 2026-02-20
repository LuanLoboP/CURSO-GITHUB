# Guia de Git e Fluxo de Trabalho

Esse documento descreve os comandos essenciais e o fluxo de trabalho que é recomendado para o desenvolvimento em equipe, assim garantindo a integridade do código e a comunicação eficiente da equipe.

Link de referência: https://youtu.be/kB5e-gTAl\_s?si=Lh-NU4zSTmQ-eSd7 => canal (

Dev Aprender | Jhonatan de Souza )

## Comandos Básicos de Versão

- Criar Versão: git commit -m "mensagem clara e curta" — Os commits são versões do seu código.

- Histórico de Versões: git reflog — Permite visualizar as versões do código, onde a versão atual é a que aparece no topo.

- Restaurar Versão: git reset --hard (id) — Volta a uma versão anterior utilizando o ID que aparece no reflog.

### Alerta de Equipe: Não mude de versão sem antes falar com o líder; se houver necessidade, comunique antes, pois trabalhar em equipe é comunicação.

## Gerenciamento de Branchs (Galhos)

Branchs são caminhos diferentes do projeto que guardam versionamentos específicos, como correções de bugs ou versões novas.

**Verificar Branch atual**: git branch — A branch ativa aparecerá em verde e com um asterisco (\*).

**Criar Nova Branch**: git branch (nome).

**Trocar de Branch**: git checkout (nome).

**Criar e Trocar**: git checkout -b (nome) — Cria uma nova branch com base na atual e já alterna para ela.

## Fluxo de Trabalho Recomendado :

Para manter o código em produção seguro, siga esta sequência rigorosa:

**Atualizar Base**: Realize um _git pull da branch principal_ para trazer a versão mais recente do servidor.

**Nova Branch**: Gere uma nova _branch_ a partir da _branch principal_.

**Desenvolvimento**: Trabalhe e adicione as novas funcionalidades na nova branch.

**Finalização**: Finalize o trabalho na branch temporária.

## Revisão e Pull Request (PR):

**Envie seu código para o servidor**: _git push --set-upstream origin (nome-da-branch)_

No GitHub, utilize o botão Compare \& pull request.

Descreva o que foi feito para facilitar a validação por outro desenvolvedor no Code Review.

## Processo de **Merge** (_União de Códigos_)

O Merge consiste em levar o código novo de uma branch de testes para a branch principal (main). Este processo deve ser realizado apenas por pessoas autorizadas.

**Sincronização**: Antes de unir os códigos, _mude para a branch_ que vai receber o código (_git checkout main_) e execute **git pull** para garantir que os códigos locais estão na versão mais atual do servidor.

**União**: Execute _git merge (nome-da-branch-revisada)_ para unir o que está correto na branch temporária à branch principal.

**Subir Alterações**: Finalize com **git push** na branch principal.

## Preparação de Arquivos (Git Add)

Defina quais arquivos serão preparados para o commit:

**Todos os arquivos**: **git add .**

**Arquivo específico**: **git add caminho/do/seu/arquivo.extensao**

**Múltiplos arquivos**: **git add arquivo1.js arquivo2.css pasta/arquivo3.html**

- **Git Ignore**

O arquivo .gitignore define o que não será adicionado ao controle de versão

Criar arquivo: touch .gitignore.

**_Uma coisa => atenção redobrada ao atualizar o código local com o servidor (git pull) evita o perigo de enviar códigos desatualizados, o que representa um risco para a empresa._**
