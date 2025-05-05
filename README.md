# Sistema de Controle de Estoque 📦

Projeto desenvolvido para a disciplina **Programação de Soluções Computacionais** da **Universidade do Sul de Santa Catarina - UNISUL**.

## 🎓 Informações Acadêmicas

- **Disciplina:** Programação de Soluções Computacionais  
- **Professores:** Osmar de Oliveira Braz Júnior, Ricardo Ribeiro Assink  
- **Avaliação:** A3 – Desempenho de compreensão  
- **Meta:** Analisar uma situação-problema, interpretar e propor soluções utilizando linguagens e técnicas de programação.  

## 👥 Integrantes do Grupo

- Arthur Zamprogna Ventura
- Gabriel Luipo            
- Nícolas Gaia Negrão      
- Pedro Henrique Francio Della Giustina
- Thiago da Silveira Gentil

## 📝 Descrição do Projeto

Este sistema foi desenvolvido com base em um problema contextualizado do cotidiano: o gerenciamento de estoque de uma empresa comercial. O software permite:

- Cadastro, edição, consulta e exclusão de produtos; `(CRUD)`
- Classificação por categorias (ex: Limpeza, Alimentos, Bebidas);
- Controle de movimentações de entrada e saída de estoque;
- Relatórios para gestão e tomada de decisão.

Sistema inspirado no projeto modelo:  
🔗 [CadastroAlunoMySQLDAO - GitHub](https://github.com/osmarbraz/CadastroAlunoMySQLDAO)

## ⚙️ Futuras Funcionalidades

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
- `db/estoque.sql`: Script SQL para criação do banco de dados

## 📂 Banco de Dados

Arquivo `estoque.sql` contendo:

- Criação das tabelas `produto`, `categoria`, `movimentacao`
- Relações entre produto e categoria
- Restrições e tipos adequados


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

1. Clone o repositório:  
   ```bash
   git clone https://github.com/PedroDella/sem1.exe.git
   ```
2. Importe o projeto na sua IDE Java (Eclipse, IntelliJ, etc.)
3. Execute o script `db/estoque.sql` no MySQL para criar as tabelas
4. Compile e execute a aplicação a partir da classe `App.java`