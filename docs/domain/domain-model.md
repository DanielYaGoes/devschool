## Usuário Interno

### O que representa?

Representa uma pessoa que acessa a área administrativa/interna do DevSchool.

Um usuário interno possui dados de identificação, credenciais de acesso e pelo menos um perfil que define suas permissões.

### Exemplos

- Administrador
- Professor

### Responsabilidades

- Acessar a área interna do sistema.
- Executar ações conforme seu perfil de acesso.
- Gerenciar recursos administrativos ou acadêmicos quando autorizado.

### Existe sozinho?

Não no contexto da aplicação interna.

Um usuário interno precisa estar vinculado a pelo menos um perfil de acesso.

### Depende de quais entidades?

- Perfil de Acesso

### Observações

Nem todo usuário interno será aluno.

O aluno será tratado separadamente, pois possui regras próprias, como matrícula, progresso e realização de listas.

## Perfil de Acesso

### O que representa?

Representa um conjunto de permissões atribuídas a um usuário interno.

### Exemplos

- Administrador
- Professor

### Responsabilidades

- Definir quais funcionalidades o usuário interno pode acessar.
- Diferenciar permissões entre administradores e professores.

### Existe sozinho?

Sim.

Um perfil pode existir antes de ser atribuído a um usuário.

### Depende de quais entidades?

Não depende de outras entidades inicialmente.

### Observações

O perfil não representa uma pessoa. Ele representa permissões.

## Aluno

### O que representa?

Representa uma pessoa que acessa a área do aluno para visualizar cursos, assistir aulas e realizar atividades.

O aluno possui dados de identificação e credenciais de acesso próprias.

### Exemplos

- Aluno matriculado em um curso

### Responsabilidades

- Acessar a área do aluno.
- Visualizar cursos em que está matriculado.
- Assistir aulas.
- Realizar listas de questões futuramente.
- Acompanhar seu progresso futuramente.

### Existe sozinho?

Sim.

Um aluno pode ser cadastrado antes de possuir matrícula em um curso.

### Depende de quais entidades?

Não depende de outras entidades inicialmente.

### Observações

Aluno e Usuário Interno possuem características semelhantes, como login e dados pessoais, mas representam contextos diferentes do sistema.

O Usuário Interno acessa a administração.

O Aluno acessa a área de estudos.

## Professor

Neste momento, Professor não será tratado como uma entidade separada.

Professor será representado como um Usuário Interno vinculado ao Perfil de Acesso PROFESSOR.

Essa decisão evita duplicação de dados e simplifica o modelo inicial.

## Curso

### O que representa?

Representa uma estrutura de ensino criada por um usuário interno.

Um curso organiza conteúdos de estudo em uma sequência lógica, permitindo que alunos tenham acesso a disciplinas, aulas e demais recursos educacionais.

Um curso possui informações próprias, como nome, descrição e carga horária.

### Exemplos

- Java para Iniciantes
- Spring Boot na Prática
- Arquitetura de Software

### Responsabilidades

- Organizar o conteúdo de ensino.
- Servir como unidade principal de estudo para o aluno.
- Agrupar disciplinas relacionadas.
- Disponibilizar o conteúdo para alunos matriculados.

### Existe sozinho?

Sim.

Um curso pode ser criado antes mesmo de possuir disciplinas, aulas ou alunos matriculados.

Durante sua construção, ele pode existir apenas com suas informações básicas.

### Depende de quais entidades?

Não depende de outras entidades para existir.

### Observações

Embora um curso possa existir sem disciplinas ou aulas, espera-se que, para ser disponibilizado aos alunos, possua uma estrutura mínima de conteúdo.

## Disciplina

### O que representa?

Representa uma área de conhecimento pertencente a um curso.

Uma disciplina organiza conteúdos relacionados sobre um determinado assunto, agrupando aulas e listas de questões.

Possui informações próprias, como nome e descrição.

### Exemplos

- Polimorfismo
- Diagramas de classe
- Concorrencia 

### Responsabilidades

- Organizar conteúdos relacionados a um mesmo assunto.
- Agrupar aulas.
- Agrupar listas de questões.
- Facilitar a organização do conteúdo de um curso.

### Existe sozinha?

Sim.

Uma disciplina pode ser criada antes mesmo de possuir aulas ou listas de questões.
### Observações

Embora uma disciplina possa existir vazia durante sua criação, espera-se que possua pelo menos uma aula ou uma lista de questões antes de ser disponibilizada aos alunos.

## Aula

### O que representa?

Representa uma unidade reutilizável de conteúdo de estudo.

Uma aula apresenta um conteúdo específico ao aluno, podendo utilizar texto, vídeo ou ambos.

A mesma aula pode ser utilizada em diferentes disciplinas quando o conteúdo for relevante para mais de um contexto.

### Exemplos

- O que são limites?
- Introdução à derivada
- Como funciona polimorfismo?

### Responsabilidades

- Apresentar um conteúdo específico ao aluno.
- Ser reutilizável em diferentes disciplinas.
- Servir como material de estudo dentro de uma ou mais disciplinas.

### Existe sozinha?

Sim.

Uma aula pode ser criada independentemente de uma disciplina.

Ela pode ser vinculada posteriormente a uma ou mais disciplinas.

### Depende de quais entidades?

Não depende de outras entidades para existir.

### Observações

A relação entre Disciplina e Aula será feita através de um vínculo.

Esse vínculo poderá armazenar informações próprias, como a ordem da aula dentro da disciplina.

## Vínculo Disciplina-Aula

### O que representa?

Representa a associação entre uma disciplina e uma aula.

Esse vínculo permite que uma mesma aula seja reutilizada em diferentes disciplinas.

### Responsabilidades

- Indicar quais aulas pertencem a uma disciplina.
- Definir a ordem das aulas dentro da disciplina.
- Permitir reutilização de aulas em diferentes disciplinas.

### Existe sozinho?

Não.

Depende de uma disciplina e de uma aula.

## Vínculo Curso-Disciplina

### O que representa?

Representa a participação de uma disciplina dentro de um curso.

Permite reutilizar uma mesma disciplina em diferentes cursos.

Também poderá armazenar informações específicas daquele vínculo, como ordem de exibição, obrigatoriedade ou outras regras futuras.

### Existe sozinho?

Não.

Depende da existência de um Curso e de uma Disciplina.

### Responsabilidades

- Relacionar cursos e disciplinas.
- Permitir reutilização de disciplinas.
- Armazenar informações específicas da relação.

## Matrícula

### O que representa?

Representa o vínculo entre um aluno e um curso.

Uma matrícula indica que um aluno possui acesso a determinado curso e poderá consumir seus conteúdos.

### Responsabilidades

- Relacionar um aluno a um curso.
- Controlar o acesso do aluno ao curso.
- Registrar informações específicas desse vínculo, como data da matrícula e status.

### Existe sozinha?

Não.

Uma matrícula depende da existência de um aluno e de um curso.

### Depende de quais entidades?

- Aluno
- Curso

### Observações

A matrícula não deve ser tratada apenas como uma tabela de ligação.

Ela representa uma regra importante do domínio, pois futuramente poderá armazenar progresso, status, conclusão ou outras informações relacionadas ao vínculo entre aluno e curso.

## Autenticação

### O que representa?

Representa o processo de identificação de quem está acessando o sistema.

### Responsabilidades

- Validar credenciais de acesso.
- Impedir acesso de pessoas não autenticadas.
- Identificar se o acesso é de um usuário interno ou de um aluno.
- Aplicar permissões conforme o perfil de acesso.

### Observações

Inicialmente haverá dois contextos de acesso:

- Área interna: Usuário Interno
- Área do aluno: Aluno

A implementação técnica será definida posteriormente.