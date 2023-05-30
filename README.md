# 🌻 **Siga o FLOW para participar do projeto**

**Para começar:** Faça um `fork` do repositório que deseja realizar alterações, o `fork` é basicamento a cópia do nosso repositório em seu próprio GitHub, onde você pode seguir seu próprio fluxo de desenvolvimento. Caso queira nos enviar suas alterações, você `DEVE` seguir alguns padrões!.

## **📋 Regras**
- Sincronize sua branch antes de criar uma `pull-request`. [veja como](#-quando-sincronizar-as-branchs)
- Siga os padrões para nomear uma branch. [veja como](#-crie-uma-nova-branch)
- Siga os padrões de commit. [veja como](#-staged---commit)

## **🤔 Quando sincronizar as branchs?**
Essa etapa é muito importante para encontrar conflitos entre os códigos e é aconselhado realizar essa sincronização todos os dias antes de continuar a realizar as alterações no código e `OBRIGATÓRIO` sempre que pretender criar uma `pull-request`. Neste WORKFLOW você pode conferir em ["Sincronizando branchs"](#-sincronizando-as-branchs).

## **🔀 FORK**
Crie um `fork` do nosso repositório para o seu GitHub e então clone seu novo repositório no seu ambiente de desenvolvimento, você pode usar seu terminal de preferência (GitBash, cmd):

Clonando repositório
```Bash
# git clone [url-do-seu-fork]
$ git clone https://github.com/Minnemi/minnemi-front.git
```

## **🔄 Instalando as dependências e executando a aplicação**

> ⚠️ Observação:
> - Realizar a instalação das dependências pode mudar de acordo com a linguagem, ferramenta ou padrão de desenvolvimento.
> - Cada repositório terá um README.md próprio que te ensina a instalar os recursos necessários para concluir este passo.
> - Para este exemplo, nós estamos usando o repositório minnemi-front.

Acessando pasta
```Bash
$ cd minnemi-front
```

Instalando dependências
```Bash
$ npm install
# ou
$ yarn install
```

Executando a aplicação
```Bash
$ npm run dev
# ou
$ yarn dev
```

## **✏️ Realizando as modificações**
A primeira coisa a se fazer é adicionar o nosso repositório como um "remote" adicional do seu repositório local com Git, isso é para facilitar a sincronização entre as branchs principals de desenvolvimento da minnemi e do seu `fork`.

Adicionando um repositório remoto com o Git:
```Bash
# git remote add [alias] [url-do-repositório]
$ git remote add minnemi https://github.com/Minnemi/minnemi-front
```

Você pode verificar a adição do novo repositório remoto assim:
```Bash
$ git config --list --local
```

Você verá algo assim na lista de configurações
`remote.minnemi.url=https://github.com/Minnemi/minnemi-front`

Você também pode encontrar o repositório remoto padrão nessa lista
`remote.origin.url=https://github.com/viniciuscosmome/minnemi-front.git`

## **📂 Crie uma nova branch**
Crie uma branch para começar a adicionar suas alterações, Siga nosso padrão para criar uma branch descritiva:
```Bash
# git checkout -b [tipo-de-alteração]/[o-que-ela-altera]
$ git checkout -b feature/database-profile-schema
```

Tipo de alteração:
- feature: adiciona nova funcionalidade
- chore: altera uma funcinoalidade existente
- fix: resolve um problema

## **💾 Staged -> Commit**
A cada etapa concluída da sua alteração é aconselhado realizar um "commit". Isso serve para que você possa apagar o que está fazendo e ainda manter as alterações anteriores.

Siga essa etapas:

Veja uma lista dos arquivos modificados
```Bash
$ git status
```

Envie os arquivos que você queira realizar o commit
- Não é aconselhado usar o `git add .(all)`
```Bash
$ git add src/styles/
```

Realize o commit das mudanças. Nós também temos um padrão de commit.
```Bash
# git commit -m "[tipo-de-mudança]: [descrição]"
$ git commit -m "chore: remove user profile scheme"
```
[Leia mais sobre o padrão de commit](https://dev.to/renatoadorno/padroes-de-commits-commit-patterns-41co)

Tipo de mudança (principais):
  - chore - mudanças em arquivos que já são controlados pelo git.
  - feat - adicionando uma nova funcionalidade, módulo, etc.
  - fix - realiza alguma correção no código.
  - refactor - realiza modificações no código sem adicionar ou alterar o comportamento do código.

A descrição do commit deve estar em inglês e deixar explícito a principal alteração no código:

- ❌ Exemplo errado:
  - "chore: changes to the .github file"
  - "chore: alteraçãos no arquivo .gitignore"
- ✅ Exemplo correto:
  - "chore: includes the .env file in the .gitignore"
  - "chore: inclui o arquivo .env no .gitignore"

## **🔄 Sincronizando as branchs**
Após realizar todas as suas alterações, chegou a hora de verificar se não há conflitos para resolver.

Primeiro, certifique-se de que seu repositório local está na branch `develop` e então execute o comando para baixar as mudanças e atualizar sua branch principal de desenvolvimento:
```Bash
# git pull [repo-remoto] [branch-do-repo-remoto]
$ git pull minnemi develop
```
Explicando:
- minnemi: é a referência ao repositório remoto que a gente criou lá no inicio desse FLOW.
- develop: é o nome da branch do repo remoto que deve ser baixada para atualizar nossa branch.

Após atualizar a branch `develop`, volte para a branch que você criou e realize a mesclagem da seguinte forma:

Voltando para branch
```Bash
$ git checkout feature/example-branch
```

Mesclando a branch com a principal
```Bash
# git merge [a-sua-branch-principal]
$ git merge develop
```
- A branch usada aqui deve ser a branch sincronizada com o repositório remoto da Minnemi.

Resolva os conflitos, se existir, e então realize o commit das mudanças.

## **🚀 Enviando sua alteração para seu repositório GitHub (o `fork`)**
Enviando alterações
```Bash
# git push [repo-remoto] [nome-da-branch-atual]
$ git push origin feature/example-branch
```

## **🔃 Pull-request**
Acesse seu repositório no GitHub, acesse a branch que acabou de enviar e crie um pull-request
<img width="75%" src="https://user-images.githubusercontent.com/48590313/241337789-2d2f5013-affa-4769-ac45-8c4e86abdba3.png" />
<img width="75%" src="https://user-images.githubusercontent.com/48590313/241337798-bb5b0fac-d732-4415-9dcd-1a27b8f23b5e.png" />

Explicando:
- base repository: repositório de destino
- base: branch que receberá o pull-request
- head repository: repositório do remetente (seu repo)
- compare: a branch com as alterações que você deseja enviar

## **🎊 Congratulations!**
Adicione a descrição da pull-request detalhando todas as alterações que ela faz e envie a requisição.
> 🆙 Nessa etapa, a descrição pode ser no seu idioma de domínio para que a escrita fique melhor, o meu é português brasileiro.
