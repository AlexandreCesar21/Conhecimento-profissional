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

<p><b>Operações:</b></p>

<p>• <b>Inserção de dados:</b></p>

<p>• <b>Consultas com </b><code>JOIN</code>:</p>

```
select * from instrutor join curso on instrutor.codigo = curso.instrutor;
select * from tipo join curso on tipo.codigo = curso.tipo;
```

<p><b>2.4. Tabela </b><code>aluno</code></p>
<p>Armazena os dados dos alunos matriculados.</p>

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
              <td>Código do aluno</td>
            </tr>
            <tr>
                <td><code>aluno</code></td>
                <td>VARCHAR(64)</td>
                <td>Nome do aluno</td>
            </tr>
            <tr>
                <td><code>endereco</code></td>
                <td>VARCHAR(128)</td>
                <td>Endereço do aluno</td>
            </tr>
             <tr>
                <td><code>email</code></td>
                <td>VARCHAR(128)</td>
                <td>E-mail do aluno</td>
            </tr>
            <tr>
                <td><code>cpf</code></td>
                <td>VARCHAR(14)	</td>
                <td>CPF do aluno</td>
            </tr>
        </tbody>
    </table>


 <p><b>Operações:</b></p>

<p>• <b>Inserção de dados:</b></p>

```
insert into aluno (aluno, endereco, email, cpf) values 
('Marcos Ferreira', 'Rua João Batista', 'marcos@gmail.com', '111.111.111-11'),
('João Vitor', 'Rua Padre Bom', 'joao@gmail.com', '222.222.222-22'),
('Alex Andrade', 'Rua Bernardo Silva', 'alex@gmail.com', '333.333.333-33'),
('Leticia', 'Rua Pão Frito', 'leticia@gmail.com', '444.444.444-44'),
('Lara Silva', 'Rua Pão Frito', 'lara@gmail.com', '555.555.555-55'),
('Laura Andrade', 'Rua Palestina', 'laura@gmail.com', '666.666.666-66'),
('Júlia Barros', 'Rua Nova', 'julia@gmail.com', '777.777.777-77');
```



<p>• <b>Consulta de dados:</b></p>

```
select * from aluno;
```


<p><b>2.5. Tabela </b><code>pedido</code></p>

<p>Armazena os pedidos realizados pelos alunos.</p>

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
                <td>Código do pedido</td>
            </tr>
            <tr>
                <td><code>aluno</code></td>
                <td>INT (FK)</td>
                <td>Código do aluno</td>
            </tr>
            <tr>
                <td><code>data</code></td>
                <td>DATE</td>
                <td>Data do pedido</td>
            </tr>
             <tr>
                <td><code>hora</code></td>
                <td>TIME</td>
                <td>Hora do pedido</td>
            </tr>
        </tbody>
    </table>


    

 <p><b>Operações:</b></p>

<p>• <b>Inserção de dados:</b></p>


```
insert into pedido (aluno, data, hora) values 
(1, '2022-10-03', '13:40:00'),
(2, '2022-10-22', '14:20:32'),
(3, '2022-11-29', '11:12:10'),
(4, '2023-01-06', '16:56:32'),
(5, '2023-02-07', '17:34:55'),
(6, '2023-02-06', '13:11:34'),
(7, '2023-01-11', '17:43:21');
```

<p>• <b>Consulta com </b><code>JOIN</code>:</p>

```
select * from aluno join pedido on aluno.codigo = pedido.aluno;
```


<p><b>2.6. Tabela </b><code>pedido_detalhe</code></p>

<p>Relaciona os cursos comprados em cada pedido.</p>



<table>
        <thead>
            <th>Campo</th>
            <th>Tipo</th>
            <th>Descrição</th>
        </thead>
        <tbody>
            <tr>
                <td><code>pedido</code></td>
                <td>INT (FK)</td>
                <td>Código do pedido</td>
            </tr>
            <tr>
                <td><code>curso</code></td>
                <td>INT (FK)</td>
                <td>Código do curso</td>
            </tr>
            <tr>
                <td><code>valor</code></td>
                <td>DOUBLE</td>
                <td>Valor do curso no pedido</td>
            </tr>
        </tbody>
    </table>


 <p><b>Operações:</b></p>

<p>• <b>Inserção de dados:</b></p>



```
insert into pedido_detalhe (pedido, curso, valor) values 
(1, 1, 1000),
(2, 2, 3000),
(3, 3, 620),
(4, 4, 4200),
(5, 5, 1330),
(6, 3, 620),
(7, 2, 1330);
```




<p>• <b>Consulta de dados:</b></p>

```
select * from pedido_detalhe;
```



<h1>Conclusão</h1>

<p>Este banco de dados foi projetado para gerenciar de forma eficiente informações de cursos, alunos, pedidos e detalhes associados, proporcionando um sistema relacional bem estruturado.</p>



