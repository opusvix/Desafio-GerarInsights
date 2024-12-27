# Bootcamp Microsoft AI for Tech – Criando Prompts Inteligentes da [DIO](https://dio.me)

## Módulo "APlicações Práticas e Ferramentas de IAs".

### Desafio de Projeto "Utilizando Prompts para Gerar Insights de Relatórios de Vendas".

Explore maneiras de utilizar prompts para transformar dados de vendas em insights valiosos, organizando informações de forma prática e eficiente.

## :abacus: Tecnologias utilizadas nesse projeto:

- [VSCode](https://code.visualstudio.com/Download)
- [GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat)
- [Python 3.x](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- No curso o instrutor utilizou o ChatGPT 4.0, então optei pela extensão do VSCode: GitHub Copilot Chat.

## :atom: Prompts:

Inicialmente, anexei as pastas de trabalho com as planilhas de vendas de três representantes de vendas;
A seguir, solicitei que o Copilot criasse prompts para transformar dados de vendas em insights valiosos, organizando informações de forma prática e eficiente. 
Como não especifiquei o formato de saída, retornou-me alguns prompts em SQL, como pode ser visto a seguir:

GitHub Copilot: Aqui estão alguns prompts que você pode usar para transformar dados de vendas em insights valiosos:

1. **Análise de Vendas por Período:**
   ```sql
   SELECT 
       DATE_FORMAT(data_venda, '%Y-%m') AS mes_ano,
       SUM(valor_venda) AS total_vendas
   FROM 
       vendas
   GROUP BY 
       mes_ano
   ORDER BY 
       mes_ano;
   ```

2. **Produtos Mais Vendidos:**
   ```sql
   SELECT 
       produto_id,
       SUM(quantidade) AS total_vendido
   FROM 
       vendas
   GROUP BY 
       produto_id
   ORDER BY 
       total_vendido DESC
   LIMIT 10;
   ```

3. **Vendas por Região:**
   ```sql
   SELECT 
       regiao,
       SUM(valor_venda) AS total_vendas
   FROM 
       vendas
   GROUP BY 
       regiao
   ORDER BY 
       total_vendas DESC;
   ```

4. **Desempenho de Vendedores:**
   ```sql
   SELECT 
       vendedor_id,
       SUM(valor_venda) AS total_vendas
   FROM 
       vendas
   GROUP BY 
       vendedor_id
   ORDER BY 
       total_vendas DESC;
   ```

5. **Comparação de Vendas Ano a Ano:**
   ```sql
   SELECT 
       YEAR(data_venda) AS ano,
       SUM(valor_venda) AS total_vendas
   FROM 
       vendas
   GROUP BY 
       ano
   ORDER BY 
       ano;
   ```

6. **Margem de Lucro por Produto:**
   ```sql
   SELECT 
       produto_id,
       SUM(valor_venda - custo_produto) AS margem_lucro
   FROM 
       vendas
   GROUP BY 
       produto_id
   ORDER BY 
       margem_lucro DESC;
   ```

7. **Taxa de Retorno de Clientes:**
   ```sql
   SELECT 
       cliente_id,
       COUNT(*) AS numero_compras,
       SUM(valor_venda) AS total_gasto
   FROM 
       vendas
   GROUP BY 
       cliente_id
   HAVING 
       numero_compras > 1
   ORDER BY 
       total_gasto DESC;
   ```

Esses prompts SQL ajudarão a organizar e analisar os dados de vendas de forma prática e eficiente, permitindo a extração de insights valiosos para a tomada de decisões.

Foram resultados excelentes! Mas refiz minha solicitação da seguinte forma: 

"Crie prompts no formato de chat para transformar dados de vendas em insights valiosos, organizando informações de forma prática e eficiente."

E o Copilt retornou o texto a seguir:
```
GitHub Copilot: Claro! Aqui estão alguns prompts no formato de chat que você pode usar para transformar dados de vendas em insights valiosos:

1. **Análise de Vendas por Período:**
   - "Quais foram as vendas totais por mês e ano?"
   - "Mostre o total de vendas agrupado por mês e ano."

2. **Produtos Mais Vendidos:**
   - "Quais são os 10 produtos mais vendidos?"
   - "Liste os produtos com as maiores quantidades vendidas."

3. **Vendas por Região:**
   - "Qual é o total de vendas por região?"
   - "Agrupe as vendas por região e mostre o total."

4. **Desempenho de Vendedores:**
   - "Quais vendedores tiveram o maior total de vendas?"
   - "Liste os vendedores ordenados pelo total de vendas."

5. **Comparação de Vendas Ano a Ano:**
   - "Como as vendas totais se comparam ano a ano?"
   - "Mostre o total de vendas agrupado por ano."

6. **Margem de Lucro por Produto:**
   - "Qual é a margem de lucro por produto?"
   - "Liste os produtos com a maior margem de lucro."

7. **Taxa de Retorno de Clientes:**
   - "Quais clientes fizeram mais de uma compra e quanto gastaram no total?"
   - "Mostre os clientes que retornaram e o total gasto por eles."

Esses prompts podem ser usados em um sistema de chat para solicitar insights específicos sobre os dados de vendas, facilitando a organização e análise das informações de forma prática e eficiente.
```
A seguir, solicitei que me desse um modelo de arquivo readme.me para aplicar no GitHub, veja a seguir:

"Com base no que foi apresentado, crie um modelo de readme.md, estruturado no formato de repositório do GitHub, apresentando esses prompts e seus resultados em formato de tabela.

A resposta foi:

GitHub Copilot: Aqui está um modelo de readme.md estruturado no formato de repositório do GitHub, apresentando os prompts e seus resultados em formato de tabela:

```markdown
# Análise de Dados de Vendas

Este repositório contém prompts para transformar dados de vendas em insights valiosos, organizando informações de forma prática e eficiente.

## Prompts e Resultados

| **Prompt** | **Descrição** | **Exemplo de Resultado** |
|------------|---------------|--------------------------|
| **Análise de Vendas por Período** | Quais foram as vendas totais por mês e ano? | `mes_ano | total_vendas`<br>`2023-01 | 10000`<br>`2023-02 | 15000` |
| **Produtos Mais Vendidos** | Quais são os 10 produtos mais vendidos? | `produto_id | total_vendido`<br>`1 | 500`<br>`2 | 450` |
| **Vendas por Região** | Qual é o total de vendas por região? | `regiao | total_vendas`<br>`Norte | 20000`<br>`Sul | 18000` |
| **Desempenho de Vendedores** | Quais vendedores tiveram o maior total de vendas? | `vendedor_id | total_vendas`<br>`1 | 30000`<br>`2 | 25000` |
| **Comparação de Vendas Ano a Ano** | Como as vendas totais se comparam ano a ano? | `ano | total_vendas`<br>`2022 | 120000`<br>`2023 | 140000` |
| **Margem de Lucro por Produto** | Qual é a margem de lucro por produto? | `produto_id | margem_lucro`<br>`1 | 5000`<br>`2 | 4500` |
| **Taxa de Retorno de Clientes** | Quais clientes fizeram mais de uma compra e quanto gastaram no total? | `cliente_id | numero_compras | total_gasto`<br>`1 | 3 | 900`<br>`2 | 2 | 700` |
```
## Como Usar

1. Clone o repositório:
   ```sh
   git clone https://github.com/seu-usuario/seu-repositorio.git
   ```
2. Navegue até o diretório do projeto:
   ```sh
   cd seu-repositorio
   ```
3. Execute os prompts SQL no seu banco de dados para obter os insights desejados.

## Contribuição

Sinta-se à vontade para contribuir com este projeto. Envie um `pull request` com suas melhorias e sugestões.

## Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

Este modelo de readme.md apresenta os prompts e seus resultados em formato de tabela, facilitando a visualização e compreensão dos insights gerados a partir dos dados de vendas.

## 👨‍💻 Autor

<p>
    <img 
      align=left 
      margin=10 
      width=80 
      src="https://avatars.githubusercontent.com/u/58704060?s=400&u=c58b05997dcd842e95dd0f5c45ab04c2054df583&v=4"
    />
    <p>&nbsp&nbsp&nbspMaurício Barros<br>
    &nbsp&nbsp&nbsp
    <a href="https://github.com/opusvix">
    GitHub</a>&nbsp;|&nbsp;
    <a href="https://www.linkedin.com/in/mauriciodasilvabarros/">LinkedIn</a>
    &nbsp;|&nbsp;
    <a href="https://x.com/opusvix">
    X</a>&nbsp;|&nbsp;
    <a href="mailto:opusvix@gmail.com">E-mail</a>
&nbsp;|&nbsp;</p>
</p>
<br/><br/>
<p>

---

:hammer_and_wrench: com :sparkling_heart: por [Maurício Barros](https://github.com/opusvix)

