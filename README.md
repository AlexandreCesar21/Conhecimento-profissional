# Sistema de Gerenciamento de Cursos e Pedidos

<p><b>Descrição</b></p>
<p>Este projeto utiliza o MySQL para criar um banco de dados que gerencia informações relacionadas a cursos, instrutores, alunos e pedidos. O sistema é organizado em tabelas relacionadas, com suporte para operações CRUD e consultas complexas entre elas.</p>

<h2>Estrutura do Banco de Dados</h2>

<p>1. Banco de Dados</p>

<p><b>• Nome: </b><code>Conhecimentos_Profissionais</code></p>

<p><b>2. Tabelas Criadas</b></p>

<p><b>2.1. Tabela</b> <code>tipo</code></p>

<p>Armazena os tipos de cursos oferecidos.</p>


<table>
        <thead>
            <th>Campo</th>
            <th>Tipo</th>
            <th>Descrição</th>
        </thead>
        <tbody>
            <tr>
                <td><code>codigo</code></td>
                <td>INT (PK, AI)</td>
              <td>Código do tipo de curso</td>
            </tr>
            <tr>
                <td><code>tipo</code></td>
                <td>VARCHAR(30)</td>
                <td>Tipo do curso</td>
            </tr>
        </tbody>
    </table>

<p><b>Operações:</b></p>


• 
<p><b>• Inserção de dados:</b></p>

```
insert into tipo (tipo) values ('Licenciatura'), ('Bacharelado'), ('Tecnólogo');
```

<p><b>• Consulta de dados:</b></p>

```
select * from tipo;
```

<p><b>2.2. Tabela </b><code>instrutor</code></p>
<p>Armazena as informações dos instrutores.</p>

<table>
        <thead>
            <th>Campo</th>
            <th>Tipo</th>
            <th>Descrição</th>
        </thead>
        <tbody>
            <tr>
                <td><code>codigo</code></td>
                <td>INT (PK, AI)</td>
              <td>Código do tipo de curso</td>
            </tr>
            <tr>
                <td><code>tipo</code></td>
                <td>VARCHAR(30)</td>
                <td>Tipo do curso</td>
            </tr>
            <tr>
                <td><code>telefone</code></td>
                <td>VARCHAR(9)</td>
                <td>Telefone do instrutor</td>
            </tr>
        </tbody>
    </table>    


<p><b>Operações:</b></p>

<p>• <b>Inserção de dados:</b></p>


```
insert into instrutor (instrutor, telefone) values 
('Gustavo Silva', '4353-3134'),
('João Freitas', '2322-1433'),
('Fernando Henrique', '1234-3211'),
('Nicole Andrade', '5654-3875'),
('Maria Silva', '6642-5255');

```

<p>• <b>Consulta de dados:</b></p>

```
select * from instrutor;

```

<p><b>2.3. Tabela </b><code>curso</code></p>

<p>Armazena os cursos disponíveis, com informações do tipo e instrutor.</p>

<table>
        <thead>
            <th>Campo</th>
            <th>Tipo</th>
            <th>Descrição</th>
        </thead>
        <tbody>
            <tr>
                <td><code>codigo</code></td>
                <td>INT (PK, AI)</td>
              <td>Código do tipo de curso</td>
            </tr>
            <tr>
                <td><code>curso</code></td>
                <td>VARCHAR(64)</td>
                <td>Nome do curso</td>
            </tr>
            <tr>
                <td><code>instrutor</code></td>
                <td>INT (FK)</td>
                <td>Código do instrutor responsável</td>
            </tr>
             <tr>
                <td><code>tipo</code></td>
                <td>INT (FK)</td>
                <td>Código do tipo do curso</td>
            </tr>
            <tr>
                <td><code>valor</code></td>
                <td>DOUBLE</td>
                <td>Valor do curso</td>
            </tr>
        </tbody>
    </table>




