# Casos de Uso - Curso

## UC-001 - Cadastrar Curso

### Objetivo

Permitir que um usuário interno autorizado cadastre um novo curso na plataforma.

O cadastro do curso será feito em etapas, permitindo que o usuário informe os dados básicos, organize disciplinas e defina professores responsáveis.

---

### Atores

- Administrador
- Professor autorizado

---

### Pré-condições

- O usuário interno deve estar autenticado.
- O usuário interno deve possuir permissão para cadastrar cursos.

---

### Fluxo Principal

1. O usuário acessa a área interna do sistema.
2. O usuário seleciona a opção de cadastrar curso.
3. O sistema apresenta a primeira etapa do cadastro.
4. O usuário informa os dados básicos do curso.
5. O sistema valida os dados informados.
6. O sistema cria o curso em estado inicial.
7. O usuário pode avançar para a etapa de vínculo de disciplinas.
8. O usuário pode vincular disciplinas existentes ao curso.
9. O usuário pode avançar para a etapa de vínculo de professores.
10. O usuário pode vincular professores responsáveis pelo curso.
11. O sistema finaliza o cadastro do curso.

---

### Dados Básicos

- Nome
- Descrição
- Carga horária
- Filtros ou categorias

---

### Regras de Negócio

- O nome do curso é obrigatório.
- A descrição do curso é obrigatória.
- A carga horária deve ser maior que zero.
- Um curso pode ser criado sem disciplinas inicialmente.
- Um curso pode ser criado sem professores vinculados inicialmente.
- Um curso recém-criado deve iniciar como rascunho ou indisponível.
- Um curso só poderá ser disponibilizado aos alunos se possuir:
    - pelo menos uma disciplina vinculada;
    - pelo menos uma aula vinculada a alguma disciplina do curso.

---

### Fluxos Alternativos

#### Dados obrigatórios não informados

O sistema informa quais campos são obrigatórios e impede a criação do curso.

#### Carga horária inválida

O sistema informa que a carga horária deve ser maior que zero.

#### Usuário pula vínculo de disciplinas

O curso permanece cadastrado, porém indisponível para os alunos.

#### Usuário pula vínculo de professores

O curso permanece cadastrado, mas sem professores responsáveis vinculados.

---

### Pós-condições

- O curso é criado no sistema.
- O curso fica disponível para edição.
- O curso permanece indisponível para alunos até possuir a estrutura mínima exigida.

---

### Observações

O cadastro em etapas permite que o curso seja criado de forma progressiva.

A disponibilização do curso para os alunos não acontece automaticamente no cadastro inicial. Ela dependerá da regra de estrutura mínima do curso.