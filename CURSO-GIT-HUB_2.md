# NESTE RESUMO FOI COLOCADO MAIS INFORMAÇÕES E MELHORADA A ORGANIZAÇÃO

## Guia de Git e Fluxo de Trabalho

Este documento descreve os comandos essenciais do Git e o fluxo de trabalho recomendado para desenvolvimento em equipe, garantindo organização, segurança do código e boa comunicação.

## Git e GitHub

**Git** *->* Ferramenta de versionamento instalada no seu computador.

**GitHub** *->* Plataforma online onde o repositório é armazenado e compartilhado.

-> **Comandos Essenciais**
-> **Verificar Status**
git status

Mostra:

Arquivos modificados

Arquivos prontos para commit

Arquivos ainda não rastreados

## Preparar Arquivos (Git Add)

Define quais arquivos irão para o próximo commit.

Todos os arquivos:

git add .

Arquivo específico:

git add caminho/do/arquivo.ext
-> **Criar Commit (Salvar Versão)**
git commit -m *"mensagem clara e objetiva"*

Um commit é como uma "foto" do projeto naquele momento.

## Boas práticas de mensagem:

feat: nova funcionalidade

fix: correção de erro

docs: documentação

refactor: melhoria interna

Exemplo:

git commit -m "feat: adiciona tela de login"
## Ver Histórico
git log

Mostra o histórico organizado de commits.

## Atualizar Projeto
git pull

Baixa e aplica as atualizações do servidor.

### Sempre faça git pull antes de começar a trabalhar.

## Enviar Código para o Servidor
git push

Envia seus commits para o GitHub.

Se for a primeira vez enviando a branch:

git push -u origin nome-da-branch
## Gerenciamento de Branches

As branches são linhas paralelas de desenvolvimento do projeto.
Permitem trabalhar em novas funcionalidades sem afetar a versão principal **que esta em produção**.

## Ver Branch Atual
git branch

A branch atual aparece com um \*.

## Criar Nova Branch
git checkout -b nome-da-branch

Cria e já troca para a nova branch.

## Trocar de Branch
git checkout nome-da-branch

feature/nome-da-funcionalidade

fix/nome-do-bug

hotfix/correcao-urgente

refactor/melhoria-interna

## Fluxo de Trabalho Recomendado

Siga esta sequência:

**1.** Atualizar a branch principal
git checkout main
git pull
**1.** Criar nova branch
git checkout -b feature/nome-da-feature
**3.** Desenvolver

Faça suas alterações normalmente.

**4.** Preparar e salvar
git add .
git commit -m "feat: descrição do que foi feito"
**5.** Enviar para o GitHub
git push -u origin feature/nome-da-feature
**6.** Criar Pull Request (PR)

No GitHub:

Clique em Compare & pull request

Descreva o que foi feito

Aguarde revisão

## Processo de Merge

O merge une a branch de desenvolvimento com a principal (main).

### Deve ser feito apenas após revisão.

Pelo GitHub (Recomendado)

Abrir Pull Request

Revisar

Clicar em Merge

Pelo Terminal
git checkout main
git pull
git merge nome-da-branch
git push

## Comandos Avançados (**Cuidado**)
Restaurar Versão
git reset --hard ID_DO_COMMIT

### Atenção:
Esse comando apaga alterações não salvas. Use com muito cuidado, *se possivel analise a situação com alguem mais experiente do time*, **sempre!!**.

-> **Ver Histórico de Movimentações**
git reflog

Mostra histórico interno do Git (mais técnico).

## .gitignore

Arquivo que define o que *NÃO* será enviado para o repositório.

Criar:

touch .gitignore

Exemplo:

node_modules/
.env
dist/

Evita subir:

Dependências

Arquivos compilados

Senhas e variáveis sensíveis

## Boas Práticas em Equipe

Sempre fazer git pull antes de começar

Nunca usar git push --force sem autorização

Não fazer merge direto na main

Sempre comunicar alterações importantes

Escrever commits claros

### Resumo do Fluxo Ideal
git checkout main
git pull
git checkout -b feature/nova-funcionalidade

# desenvolver

git add .
git commit -m "feat: nova funcionalidade"
git push -u origin feature/nova-funcionalidade

Abrir Pull Request → Revisão → Merge
