<h1>Processamento de dados com Power BI.  </h1> 
<h2>Desafio 3 - Criando relatório com integração com Mysql e Azure.
<p></p>
Objetivo:</h2>

<p>Este projeto foi desenvolvido como parte do bootcamp NTT DATA Engenharia de Dados com Python, oferecido pela Digital Innovation One (DIO). O foco deeste desafio é criar um relatório integrando as tecnoligias Azure e Mysql.</p>
-------------------------------------------------------

-------------------------------------------------------
Funcionalidades do Relatório.
O relatório foi dividido em dois principais painéis:

<h3>1 - Relatório de Colaboradores </h3>

-Essa página oferece uma visão detalhada dos colaboradores, gerentes e departamentos da empresa. As visualizações incluem o custo salarial por departamento, a distribuição dos colaboradores por gerentes e departamentos, além da quantidade de dependentes por colaborador.
-------------------------------------------------------
![pagina1](https://github.com/user-attachments/assets/611c74db-f183-45b6-8ea2-ac60f56ec6a7)
------------------------------------------------------
- Para realizar a mesclagem entre as tabelas 'employee' e 'departament' foi realizado o seguinte código sql:
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
-------------------------------------------------------
![powerbi](https://github.com/user-attachments/assets/13fb3da4-5ecc-4a9a-90d5-4b1469a8ca1f)
------------------------------------------------------

<h3>2 - Relatório de Projetos</h3>

- O foco desta página é mostrar os projetos em andamento na organização. Inclui o custo salarial associado a cada projeto, a distribuição dos projetos por departamento, o total de horas trabalhadas e a localização dos departamentos responsáveis. A análise permite ver quais projetos demandam mais recursos e qual departamento está mais envolvido.

-------------------------------------------------------
![powerbi](https://github.com/user-attachments/assets/fe58dce6-85ff-4352-b9ed-f4d8ea4378e3)
-------------------------------------------------------

- Foi usado o processo de mesclagem 

## Tecnologia usada.

- **Power BI** - Ferramenta de visualização de dados utilizada para criar os relatórios interativos.
-----------------------------------------------------------
### Como Executar:

1 - Faça o download do arquivo .pbix (Relatorios_com_Power_BI).

2 - Abra o arquivo no Power BI Desktop.

3 - Navegue pelas páginas para visualizar distribuição de colaboradores e projetos.

4 - Utilize filtros interativos para explorar os dados em profundidade.
