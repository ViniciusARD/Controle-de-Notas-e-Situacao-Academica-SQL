# Controle de Notas e Situação Acadêmica - SQL

Este projeto foi desenvolvido como um exercício prático de banco de dados, envolvendo a criação e manipulação de tabelas para gerenciamento de informações acadêmicas. Ele abrange as tabelas de cursos, alunos, disciplinas, tipos de notas, notas dos alunos e situações acadêmicas, além de funções SQL para operações avançadas, como inserção de notas e verificação de tipos de notas.

## Estrutura do Banco de Dados

O banco de dados contém as seguintes tabelas:

1. **Curso**
   - `id`: Identificador único do curso (PK).
   - `nome`: Nome do curso.

2. **Aluno**
   - `rgm`: Número de registro do aluno (PK).
   - `nome`: Nome do aluno.
   - `curso`: Identificador do curso (FK).

3. **Disciplina**
   - `codigo`: Código único da disciplina (PK).
   - `nome`: Nome da disciplina.

4. **TipoNota**
   - `codigo`: Código único do tipo de nota (PK).
   - `nome`: Nome do tipo de nota (p1, p2, exame).

5. **Notas**
   - `id`: Identificador único da nota (PK).
   - `rgm_aluno`: Número de registro do aluno (FK).
   - `codigo_disciplina`: Código da disciplina (FK).
   - `tipo_nota`: Código do tipo de nota (FK).
   - `nota`: Valor da nota (até 2 casas decimais).

6. **Situação**
   - `aluno`: Número de registro do aluno (FK).
   - `situacao`: Situação acadêmica do aluno (aprovado, reprovado, cursando, dp).
   - `disciplina`: Código da disciplina (FK).
   - `id`: Identificador único da situação (PK).

## Consultas e Funções SQL

O arquivo `Controle_de_Notas.sql` contém as seguintes consultas e funções SQL:

### Exemplos de Consultas

1. **Função `primeira`**
   - Retorna as notas do tipo especificado (ex: 'p2') para um aluno.
   ```sql
   select * from primeira ('p1');
   ```

2. **Função `existetipo`**
   - Verifica se um tipo de nota existe no banco de dados.
   ```sql
   select existetipo ('p1');
   ```

3. **Função `inserenota`**
   - Insere uma nova nota para um aluno, após verificar se o tipo de nota existe.
   ```sql
   select inserenota (10, 1, 1, 'p1', 5);
   ```

4. **Função `inserenota2`**
   - Alternativa para a função `inserenota`, realizando a inserção com um controle de tipos de nota.
   ```sql
   select inserenota2 (11, 1, 1, 'p2', 6);
   ```

### Tabelas e Inserções

- As tabelas são criadas e populadas com dados de exemplo sobre cursos, alunos, disciplinas, tipos de notas, notas e situação acadêmica dos alunos.
- Os dados de exemplo incluem alunos, disciplinas e as notas atribuídas nas provas (p1 e p2).

## Como Usar

1. Clone o repositório:
   ```bash
   git clone https://github.com/ViniciusARD/Controle-de-Notas-SQL.git
   ```

2. Execute o script SQL em um SGBD de sua preferência (ex: MySQL, PostgreSQL).

3. Explore as funções SQL e consulte as tabelas para entender melhor a gestão das notas e a situação acadêmica.

## Tecnologias Utilizadas

- SQL (Structured Query Language)
- PostgreSQL
