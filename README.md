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
            <th scope="col" class="titulo">Campo</th>
            <th scope="col" class="titulo">Tipo</th>
            <th scope="col" class="titulo">Descrição</th>
        </thead>
        <tbody>
            <tr>
                <td class="pesobaixo">codigo</td>
                <td class="pesobaixo">INT (PK, AI)</td>
              <td class="pesobaixo">Código do tipo de curso</td>
            </tr>
            <tr>
                <td class="pesonormal">Peso normal</td>
                <td class="pesonormal">18,5 e 24,9</td>
            </tr>
            <tr>
                <td class="sobrepeso">Sobrepeso</td>
                <td class="sobrepeso">25 e 29,99</td>
            </tr>
            <tr>
                <td class="obesidadegrauI">Obesidade grau I</td>
                <td class="obesidadegrauI">30 e 34,99</td>
            </tr>
            <tr>
                <td class="obesidadegrauII">Obesidade grau II (Servera)</td>
                <td class="obesidadegrauII">35 e 39,99</td>
            </tr>
            <tr>
                <td class="obesidadegrauIII">Obesidade grau III (Mórbida)</td>
                <td class="obesidadegrauIII">Acima de 40</td>
            </tr>
        </tbody>
    </table>
