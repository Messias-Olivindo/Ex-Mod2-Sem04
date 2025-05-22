# Módulo 2 Aula 04 

Explicação de alguns conceitos utilizados durante o exercício e desenvolvimento do projeto

## Models

Models é o elemento da arquitetura MVC responsável por realizar as ações no banco de dados de acordo com as requisições passadas pelo Controller

- models/aluno.js

Responsável por fazer o CRUD na tabela aluno de acordo com o que é passado pelo controllers/alunoController.js

- models/curso.js

Responsável por fazer o CRUD na tabela curso de acordo com o que é passado pelo controllers/cursoController.js

- models/professor.js

Responsável por fazer o CRUDO na tabela professor de acordo com o que é passado pelo controllers/professorController.js 

## Controller

- controllers/alunoController.js

Responsável por mandar as ações que o models/aluno.js deve fazer de acordo com o que o usuário selecionar no views/alunos/index.ejs.

- controllers/cursoController.js

Responsável por mandar as ações que o model deve fazer de acordo com o que o usuário selecionar no views/alunos/index.ejs.

- controllers/professorController.js

Responsável por mandar as ações que o model deve fazer de acordo com o que o usuário selecionar no view.

# Módulo 2 Aula 06

1. **Explique com suas palavras o papel de cada camada da arquitetura MVC usada neste projeto.**
*Como o Model, o Controller e a View interagem entre si?*

- O Model é responsável por fazer as requisições no banco de dados de acordo com a tabela e as ações que são passadas pelo controller. O controller é responsável por fazer a intermediação do views e models, passando as requisições para os models e mandando o resultado para o views. Já o views retorna a formulação das requisições de maneira visual e o resultado dessas ações.

2. **Como ocorre o envio e o recebimento de dados no formato JSON neste projeto?**
*Cite uma rota que responde em JSON e explique seu funcionamento*

- Em controllers/alunoController aparece uma resposta em JSON. Serve para mostrar os alunos de um curso por meio do id do curso e os alunos cadastrados nele.

```
exports.byCurso = async (req, res) => {
  const { curso_id } = req.params;
  const alunos = await Aluno.findByCurso(curso_id);
  res.json(alunos);
};

```

3. **Qual a importância de usar HTML básico com formulários e tabelas para organizar e manipular dados no navegador**
*Por que esse tipo de estrutura ainda é útil em projetos back-end com Node.js*

- É importante para demonstrar as informações para melhorar a visualização das informações por meio de tabelas e o uso de formulários facilita o processo de CRUD no banco de dados.