# Sistema de Controle de Estoque 📦

Projeto desenvolvido para a disciplina **Programação de Soluções Computacionais** da **Universidade do Sul de Santa Catarina - UNISUL**.

## 🎓 Informações Acadêmicas

- **Disciplina:** Programação de Soluções Computacionais
- **Professores:** Osmar de Oliveira Braz Júnior, Ricardo Ribeiro Assink
- **Avaliação:** A3 – Desempenho de compreensão
- **Meta:** Analisar uma situação-problema, interpretar e propor soluções utilizando linguagens e técnicas de programação.

## 👥 Integrantes do Grupo

- Arthur Zamprogna Ventura - 10725111773 - @arthurventuraza
- Gabriel Luipo - 1072519471 - @euluipo
- Nícolas Gaia Negrão
- Pedro Henrique Francio Della Giustina - 10725110773 - @PedroDella
- Thiago da Silveira Gentil - 1072112389 - @Tgentil

## 📝 Descrição do Projeto

Este sistema foi desenvolvido com base em um problema contextualizado do cotidiano: o gerenciamento de estoque de uma empresa comercial. O software permite:

- Cadastro, edição, consulta e exclusão de produtos; `(CRUD)`
- Classificação por categorias (ex: Limpeza, Alimentos, Bebidas);
- Controle de movimentações de entrada e saída de estoque;
- Relatórios para gestão e tomada de decisão.

Sistema inspirado no projeto modelo:  
🔗 [CadastroAlunoMySQLDAO - GitHub](https://github.com/osmarbraz/CadastroAlunoMySQLDAO)

## ⚙️ Funcionalidades

- **CRUD de Produtos**
- **CRUD de Categorias**
- **Movimentação de Estoque (Entrada/Saída)**
- **Reajuste de preços em massa por percentual**
- **Geração dos relatórios:**
  - Lista de Preços
  - Balanço Físico/Financeiro
  - Produtos abaixo da quantidade mínima
  - Produtos acima da quantidade máxima
  - Quantidade de produtos por categoria

## 🛠️ Tecnologias e Ferramentas Utilizadas

- **Linguagem:** Java
- **IDE:** IntelliJ IDEA / NetBeans
- **Banco de Dados:** MySQL
- **Padrão de Acesso a Dados:** DAO (Data Access Object)
- **Controle de Versão:** Git + GitHub

## 🧱 Estrutura do Projeto

- `src/model`: Classes de entidade (Produto, Categoria, Movimentação)
- `src/view`: Telas e interface gráfica (Swing)
- `src/dao`: Classes de persistência e consultas ao banco
- `src/util`: Classes utilitárias (Validador, GeradorRelatorio)
- `db/estoque.sql`: Script SQL para criação do banco de dados

## 📂 Banco de Dados

Arquivo `estoque.sql` contendo:

- Criação das tabelas `produto`, `categoria`, `movimentacao`
- Relações entre produto e categoria
- Restrições e tipos adequados
- Dados de exemplo para testes

## 📊 Relatórios Gerados

- `Relatório de Preços`
- `Balanço Físico/Financeiro`
- `Produtos Abaixo do Mínimo`
- `Produtos Acima do Máximo`
- `Total por Categoria`

## 📌 Observações Finais

- O projeto foi desenvolvido colaborativamente com versionamento no GitHub.
- As mensagens de commit seguem convenções claras.
- O código foi padronizado conforme boas práticas de organização e legibilidade.

## 📁 Como Executar o Projeto

### Pré-requisitos

- Java JDK 11 ou superior
- IDE Java (IntelliJ IDEA recomendado)
- MySQL Server instalado e em execução

### Passo a Passo

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/PedroDella/SistemasControleEstoque
   ```

2. **Configure o banco de dados:**
  - Certifique-se de que o MySQL Server esteja instalado e em execução
  - Abra o MySQL Command Line Client ou MySQL Workbench
  - Crie o banco de dados e execute o script SQL:
    ```sql
    CREATE DATABASE controle_estoque;
    USE controle_estoque;
    source caminho/para/db/estoque.sql
    ```
  - Alternativamente, no MySQL Workbench, vá em File > Open SQL Script, selecione o arquivo `db/estoque.sql` e execute-o

3. **Configure a conexão com o banco de dados:**
  - Abra o arquivo `src/dao/ConnectionFactory.java`
  - Ajuste as constantes de conexão conforme sua configuração:
    ```java
    private static final String DRIVER = "com.mysql.cj.jdbc.Driver";
    private static final String URL = "jdbc:mysql://localhost:3306/controle_estoque";
    private static final String USER = "seu_usuario"; // Altere para seu usuário MySQL
    private static final String PASS = "sua_senha";   // Altere para sua senha MySQL
    ```

4. **Importe o projeto na sua IDE:**
  - No IntelliJ IDEA: File > Open > Selecione a pasta do projeto
  - Adicione o driver JDBC do MySQL ao projeto:
    - File > Project Structure > Libraries
    - Clique no "+" e selecione "From Maven"
    - Pesquise por "mysql-connector-java" e adicione a versão mais recente

5. **Execute a aplicação:**
  - Navegue até a classe `src/view/App.java`
  - Clique com o botão direito e selecione "Run 'App.main()'"
  - A interface gráfica do sistema será iniciada

### Solução de Problemas

- Se ocorrer erro de conexão com o banco de dados:
  - Verifique se o MySQL está em execução
  - Confirme se as credenciais em ConnectionFactory.java estão corretas
  - Certifique-se de que o banco de dados `controle_estoque` foi criado

- Se ocorrer erro de ClassNotFoundException:
  - Verifique se o driver JDBC do MySQL foi adicionado corretamente ao projeto

# Requisitos do Sistema de Controle de Estoque

## Requisitos Funcionais

### Produto
- Cadastro de produtos (CRUD)
- Atributos: Nome, Preço unitário, Unidade, Quantidade em estoque, Quantidade mínima, Quantidade máxima, Categoria
- Reajuste de preços em massa por percentual

### Categoria
- Cadastro de categorias (CRUD)
- Atributos: Nome, Tamanho (Pequeno, Médio, Grande), Embalagem (Lata, Vidro, Plástico)

### Movimentação de Estoque
- Registro de entradas e saídas de produtos
- Atualização automática do saldo em estoque
- Alertas quando quantidade abaixo do mínimo (saída) ou acima do máximo (entrada)

### Relatórios
- Lista de Preços: produtos em ordem alfabética com preço, unidade e categoria
- Balanço Físico/Financeiro: produtos, quantidade, valor total por produto e valor total do estoque
- Produtos abaixo da quantidade mínima
- Produtos acima da quantidade máxima
- Quantidade de produtos por categoria

## Regras de Negócio
- Saída de produto: subtrai quantidade do estoque
- Entrada de produto: adiciona quantidade ao estoque
- Alertar quando estoque abaixo do mínimo durante saída
- Alertar quando estoque acima do máximo durante entrada
- Não é necessário cadastrar clientes ou fornecedores

## Requisitos Técnicos
- Linguagem: Java
- IDE: IntelliJ IDEA / NetBeans
- Banco de Dados: MySQL
- Padrão de Acesso a Dados: DAO (Data Access Object)
- Controle de Versão: Git + GitHub
- JDK 11 ou superior

## Convenções de Código
- Nome de classes em CamelCase
- Nome de pacotes em letras minúsculas
- Comentários explicativos
- Nomenclatura em português
- Clean Code

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

