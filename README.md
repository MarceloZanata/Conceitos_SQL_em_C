# Motor de Banco de Dados Relacional em Linguagem C

## Visão Geral
Este software, desenvolvido inteiramente em C, funciona como um sistema de gerenciamento de dados para a malha metroferroviária de São Paulo. A aplicação provê infraestrutura para leitura e escrita em arquivos binários, execução de consultas complexas, indexação de registros e reciclagem de espaço físico para otimização de performance em disco.

## Funcionalidades
- **Persistência de Dados:** Processamento de bases CSV, conversão para formato binário proprietário e rotinas de leitura, inserção e atualização de registros.
- **Recuperação de Espaço:** Controle de registros deletados logicamente através de uma estrutura de pilha, permitindo sobrescrever espaços vazios e evitar fragmentação.
- **Buscas Indexadas:** Integração de uma estrutura de Árvore-B (B-Tree) para localização instantânea de estações via chaves de identificação.
- **Cruzamento de Tabelas (Joins):** Mecanismo de junção de arquivos para relacionar diferentes entidades por meio de três abordagens clássicas:
    - *Nested Loop Join* (comparação por força bruta).
    - *Index Join* (busca direta acelerada pela Árvore-B).
    - *Sort-Merge Join* (intercalação baseada em ordenação prévia).

## Arquitetura e Modelagem
O domínio do projeto abrange as estações, linhas, distâncias e conexões do transporte paulista. Visando contornar os gargalos físicos de leitura e escrita (I/O) inerentes ao baixo nível, a modelagem de dados adota uma estratégia de desnormalização. Isso concentra as informações e exige que as redundâncias de dados sejam tratadas e resolvidas diretamente pela lógica do código fonte.

## Instruções de Uso
- `make all`: Compila todo o código-fonte do projeto.
- `make run`: Inicializa o programa principal no terminal.
- `make clean`: Remove os binários compilados e arquivos temporários.
