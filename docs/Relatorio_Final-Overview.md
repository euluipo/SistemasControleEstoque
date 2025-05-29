# Relatório Final - Sistema de Controle de Estoque

## Visão Geral do Projeto

Este projeto implementa um Sistema de Controle de Estoque conforme os requisitos fornecidos. O sistema foi desenvolvido seguindo as melhores práticas de programação.

## Estrutura do Projeto

O projeto foi organizado seguindo o padrão DAO (Data Access Object) e a arquitetura MVC (Model-View-Controller), com os seguintes pacotes:

- **model**: Classes que representam as entidades do sistema
- **dao**: Classes responsáveis pelo acesso a dados
- **view**: Classes de interface gráfica
- **util**: Classes utilitárias

## Funcionalidades Implementadas

### Classes de Modelo
- **Categoria**: Representa uma categoria de produtos com atributos como nome, tamanho e embalagem
- **Produto**: Representa um produto com atributos como nome, preço, quantidades e categoria
- **Movimentacao**: Representa uma movimentação de estoque (entrada ou saída)

### Classes DAO
- **ConnectionFactory**: Gerencia conexões com o banco de dados
- **CategoriaDAO**: Operações CRUD e consultas específicas para categorias
- **ProdutoDAO**: Operações CRUD e consultas específicas para produtos
- **MovimentacaoDAO**: Operações CRUD e consultas específicas para movimentações

### Classes Utilitárias
- **Validador**: Métodos para validação de dados de entrada
- **GeradorRelatorio**: Métodos para geração dos relatórios solicitados

### Interface Gráfica
- **TelaPrincipal**: Menu principal do sistema com acesso a todas as funcionalidades
- **App**: Classe principal que inicia a aplicação

## Banco de Dados

O script SQL para criação do banco de dados está disponível em `db/estoque.sql`. Ele cria as tabelas necessárias e insere alguns dados de exemplo para testes.

## Boas Práticas Aplicadas

1. **Clean Code**:
   - Nomes significativos em português
   - Métodos pequenos e com responsabilidade única
   - Comentários explicativos
   - Tratamento adequado de exceções

2. **Encapsulamento**:
   - Atributos privados com getters e setters
   - Validação de dados antes de persistência

3. **Documentação**:
   - Comentários JavaDoc em todas as classes e métodos
   - Explicações claras sobre o propósito e funcionamento

4. **Organização**:
   - Estrutura de pacotes lógica e organizada
   - Separação clara de responsabilidades

## Como Executar o Projeto

1. Importe o projeto no IntelliJ IDEA
2. Configure o MySQL e execute o script `db/estoque.sql`
3. Ajuste as configurações de conexão em `ConnectionFactory.java` se necessário
4. Execute a classe `App.java` para iniciar o sistema

## Próximos Passos

Para completar a implementação, seria necessário:

1. Implementar as telas específicas de cadastro e consulta
2. Conectar as interfaces gráficas com as classes DAO
3. Implementar a geração de relatórios na interface
4. Adicionar validações na camada de visualização

## Conclusão

O projeto foi estruturado seguindo as melhores práticas de desenvolvimento, com código limpo, bem documentado e em português. A arquitetura escolhida permite fácil manutenção e extensão do sistema para atender a novos requisitos no futuro.
