Projeto Imobiliária – Manipulação de Dados com Pandas

Este projeto tem como objetivo **manipular e transformar dados imobiliários** para enriquecer a análise e gerar novas informações relevantes.
Foram adicionadas colunas calculadas, descrições detalhadas dos imóveis e variáveis categóricas para facilitar estudos futuros.

Objetivos do Projeto:

* Carregar a base de dados de imóveis para aluguel.
* Criar novas variáveis derivadas dos dados originais.
* Adicionar descrições detalhadas de cada imóvel.
* Classificar imóveis conforme características específicas.
* Exportar os resultados para arquivos CSV.

Estrutura do Projeto:

1. **Importação da Base de Dados**

   * Leitura do dataset `aluguel.csv`.

2. **Criação de Novas Colunas**

   * `Valor_por_mês` → Soma do valor do aluguel + condomínio.
   * `Valor_por_ano` → Valor anual do aluguel, incluindo IPTU.
   * `Descrição` → Texto descritivo de cada imóvel (tipo, bairro, quartos e vagas).
   * `Possui_suite` → Variável categórica indicando se o imóvel possui suíte.

3. **Exportação dos Dados**

   * Arquivo final `dados_dev.csv` contendo a base enriquecida.

Tecnologias Utilizadas:

* **Python 3**
* **Pandas**
* Google Colab

Exemplos de Transformações:

**Coluna `Valor_por_mês`:**

```python
dados['Valor_por_mês'] = dados['Valor'] + dados['Condominio']
```

**Coluna `Descrição`:**

```python
dados['Descrição'] = dados['Tipo'] + ' em ' + dados['Bairro'] + ' com ' + \
                     dados['Quartos'].astype(str) + ' quarto(s) e ' + \
                     dados['Vagas'].astype(str) + ' vaga(s) de garagem.'
```

**Coluna `Possui_suite`:**

```python
dados['Possui_suite'] = dados['Suites'].apply(lambda x: 'Sim' if x > 0 else 'Não')
```

Resultado Final:

* `dados_dev.csv` → Base de dados enriquecida com novas colunas.

Fonte dos Dados:

Os dados originais foram disponibilizados pela [Alura Cursos](https://github.com/alura-cursos/pandas-conhecendo-a-biblioteca).

Autor:

Desenvolvido por **Igor Gomes Leopoldino**
Contato: [igorleopoldino18@gmail.com](mailto:seuemail@email.com)
[LinkedIn](https://linkedin.com/in/igor-leopoldino/)
