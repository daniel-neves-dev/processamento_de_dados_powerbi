<h1>Processamento de Dados com Power BI</h1> 

<h2>Desafio 3 - Criando Relatório Usando Integração com MySQL e Azure
<p></p>
Objetivo:</h2>

<p>Este projeto foi desenvolvido como parte do bootcamp NTT DATA Engenharia de Dados com Python, oferecido pela Digital Innovation One (DIO). O foco deste desafio é criar um relatório integrando as tecnologias Azure e MySQL.</p>
<p>O banco de dados foi criado diretamente no Dash Terminal do Azure.</p>

<h4>Ecemplo em imagens do Azure</h4>

-------------------------------------------------------
<div>
  <img src="https://github.com/user-attachments/assets/197f18b9-e34e-4745-9917-7b4553f07659" alt="Descrição da imagem 1">
</div>
<div style="width:30%; display: flex;">
  <div>
    <img src="https://github.com/user-attachments/assets/3ccd3f63-4949-45f9-b102-0ebdf312a85a" alt="Descrição da imagem 2">
  </div>
  <div>
    <img src="https://github.com/user-attachments/assets/04e110f6-0a52-4176-9560-fcc7b003675f" alt="Descrição da imagem 3">
  </div>
</div>

-------------------------------------------------------

## Funcionalidades do Relatório

O relatório foi dividido em dois principais painéis:

### 1. Relatório de Colaboradores

<p>Essa página oferece uma visão detalhada dos colaboradores, gerentes e departamentos da empresa. As visualizações incluem o custo salarial por departamento, a distribuição dos colaboradores por gerentes e departamentos, além da quantidade de dependentes por colaborador.</p>

-------------------------------------------------------
![pagina1](https://github.com/user-attachments/assets/611c74db-f183-45b6-8ea2-ac60f56ec6a7)
-------------------------------------------------------

- Para realizar a mesclagem entre as tabelas 'employee' e 'department', foi utilizado o seguinte código SQL:

```sql
SELECT
  e.Fname AS Employee_FirstName, 
  e.Lname AS Employee_LastName, 
  e.Ssn AS Employee_Ssn, 
  s.Fname AS Supervisor_FirstName, 
  s.Lname AS Supervisor_LastName, 
  s.Ssn AS Supervisor_Ssn 
FROM 
  employee e 
LEFT JOIN 
  employee s ON e.Super_ssn = s.Ssn;
```

-------------------------------------------------------
![powerbi](https://github.com/user-attachments/assets/fe58dce6-85ff-4352-b9ed-f4d8ea4378e3)
-------------------------------------------------------

<h3>2 - Relatório de Projetos</h3>

<p>O foco desta página é mostrar os projetos em andamento na organização. Inclui o custo salarial associado a cada projeto, a distribuição dos projetos por departamento, o total de horas trabalhadas e a localização dos departamentos responsáveis. A análise permite ver quais projetos demandam mais recursos e qual departamento está mais envolvido.</p>

-------------------------------------------------------
![pagina2](https://github.com/user-attachments/assets/5ee783c0-85f2-4296-b663-fac47819645c)
-------------------------------------------------------

<p>Foi utilizado o processo de mesclagem entre os campos 'department' e 'location'.</p>
<p>Por que, neste caso, podemos utilizar o mesclar e não o atribuir?</p>
<p>Ao mesclar os nomes de "Departamento" e "Localização", estamos criando uma nova coluna que combina esses dois campos em um único valor, tornando cada combinação única. O motivo pelo qual utilizamos a função Mesclar e não a função Atribuir é que o Mesclar cria um novo campo combinando as informações de duas ou mais colunas, sem perder os dados originais. Isso é importante porque queremos garantir que cada combinação de "Departamento" e "Localização" seja única para cada registro, o que é fundamental para a criação de um modelo estrela em futuros módulos.</p>
<p>A função Atribuir geralmente é usada para atribuir valores diretamente, substituindo ou definindo valores em uma coluna com base em uma condição ou fórmula, o que não atenderia nosso objetivo de manter as informações originais e criar uma combinação única. Neste caso, a Mesclagem nos permite criar uma chave composta útil para relacionar as tabelas e construir um modelo de dados bem estruturado para análises futuras.</p>

-----------------------------------------------------------
### Tecnologias Utilizadas:

<p>Power BI - Ferramenta de visualização de dados utilizada para criar os relatórios interativos.</p>
<p>MySQL - Sistema de gerenciamento de banco de dados relacional.</p>
<p>Azure - Plataforma de serviços em nuvem da Microsoft utilizada para integrar e hospedar os dados.</p>

-----------------------------------------------------------
### Como Executar:

1 - Faça o download do arquivo .pbix (Processamento de Dados).

2 - Abra o arquivo no Power BI Desktop.

3 - Navegue pelas páginas para visualizar distribuição de colaboradores e projetos.

4 - Utilize filtros interativos para explorar os dados em profundidade.
