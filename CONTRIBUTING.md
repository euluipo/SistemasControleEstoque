# Contribuindo para o Sistema de Controle de Estoque - UNISUL

Abaixo estão algumas diretrizes importantes para garantir uma colaboração eficiente e organizada.

## 📋 Como Contribuir

### Reportando Problemas ou Bugs

- Utilize a aba **Issues** do GitHub para relatar comportamentos inesperados ou erros.
- Explique claramente o problema e, se possível, inclua:
  - Passos para reproduzir o erro
  - Capturas de tela ou mensagens de erro
  - Trechos de código relacionados

### Sugerindo Melhorias

- Antes de implementar, abra uma **Issue** para descrever a ideia.
- Justifique a importância da sugestão e indique como ela contribui para o objetivo do projeto.

## ⚙️ Configuração do Projeto

### Pré-requisitos

- Java JDK 11 ou superior
- IDE Java (recomendado: IntelliJ IDEA ou netBeans)
- MySQL Server ativo

### Instruções de Instalação e Execução

1. **Clone este repositório:**
   ```bash
   git clone https://github.com/PedroDella/sem1.exe.git
   ```

2. **Importe o projeto em sua IDE Java**

3. **Configure o banco de dados executando o script SQL:**
   - Caminho: `db/estoque.sql`

4. **Compile e execute o projeto**
   - A classe principal é `App.java`

## 🚀 Enviando Pull Requests

- Crie um branch a partir da `main` com um nome descritivo:
  ```bash
  git checkout -b feature/descricao-funcionalidade
  ```

- Siga as convenções de codificação Java e o padrão do projeto.
- Faça commits claros e frequentes com mensagens explicativas:
  ```
  feat: adicionar funcionalidade de relatório financeiro
  fix: corrigir bug na atualização de estoque
  ```

- Atualize a documentação e arquivos `.md` quando necessário.
- Ao concluir, abra um Pull Request detalhado e associe à Issue correspondente, se houver.

## 🧑‍💻 Convenções de Código

- Padrão DAO para persistência
- Nome de classes em **CamelCase**
- Nome de pacotes em **letras minúsculas**
- Comentários explicativos sempre que necessário

## 📜 Código de Conduta

Este projeto segue diretrizes de respeito, colaboração e ética acadêmica. Espera-se que todas as interações sejam cordiais e construtivas.
