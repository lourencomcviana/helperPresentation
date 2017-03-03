#HSLIDE
# Módulo Help
O Módulo "Help" é um conjunto de providers, serviços e
diretivas feitos para gerênciar os tópicos de ajuda
em uma aplicação angular. 

#HSLIDE
## O que é?
O Helper trabalha com arquivos no formato **[markdown](https://guides.github.com/features/mastering-markdown/)**. Um arquivo
markdown deve existir e estar acessível por URL.
#HSLIDE
Graças a característica acima. Um sistema pode adicionar índices de ajuda
de outros sistema (um sistema que gera DAE pode importar a ajuda do dae do sistema responsável por gerar DAE. Ou até direto da wiki externa do gitlab)
#HSLIDE
É possível adicionar arquivos markdown diretamente no formato string. Porém não é recomendado! Pois
o índice de ajuda criado não seria compartilhável e ficaria difícil de editar mais tarde.


#HSLIDE
## Dependências
- [ng-showdown](http://x-oc-config.sefa.pa.gov.br/gitlab/sefa/sefa-ui/wikis/showdown): interpretador de markdown [documentação oficial](https://github.com/showdownjs/ng-showdown)
- [ngDexie](http://x-oc-config.sefa.pa.gov.br/gitlab/sefa/sefa-ui/wikis/dexie): Controla os tópicos de ajuda no banco local(indexDB) da máquina do usuário utilizando o framework dexiejs
- [mapper](#): Mapeia json para classes bem definidas. Uso interno

#HSLIDE
## Classes
Help, Search, Summary
#VSLIDE
### Help
``` json
{
    "id":"chave do help",
    "title":["sub sub titulo","sub titulo","titulo do help"],
    "tags":["lista","de","tags"],
    "path":"/caminho/para/o/arquivo.md",
    "document":"documento carregado.",
    "order":"ordem do help, caso não definida será considerada a ordem de inserção na base"
    "version":"versão do documento. Controlado automaticamente"
}
```
#VSLIDE
### Search
``` json
{
    "id":"chave do help",
    "title": "titulo do help",
    "tags":["lista","de","tags"],
    "path":"/caminho/para/o/arquivo.md",
    "order":"ordem do help"
}
```
#VSLIDE
### Summary
``` json
*Em desenvolvimento*
```
#HSLIDE
## Providers e services 
Todos os métodos retornam [**Promessas**](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Promise)

Tipo     | Fonte        | Método | Parâmetros                        | Retorno
---------| ------------ | ------ | --------------------------------- | -----------
Provider | helpProvider | add    | [Help]() or [[Help]()]            | N/A
Provider | helpProvider | delete | N/A                               | N/A
Service  | help         | get    | [Search]()                        | [Help]      
#VSLIDE
Tipo     | Fonte        | Método | Parâmetros                        | Retorno
---------| ------------ | ------ | --------------------------------- | -----------
Service  | help         | update | N/A                               | [String]
Service  | helpDialog   | show   | Mesmos o método [help.get]()      | N/A
Service  | helpSummary  |        |  |

#HSLIDE
## Documentação
(helper)[http://x-oc-config.sefa.pa.gov.br/gitlab/sefa/sefa-ui/wikis/helper]