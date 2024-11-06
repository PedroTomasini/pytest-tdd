# Projeto: pytest-tdd

Este é um projeto de exemplo para prática de Test-Driven Development (TDD) em Python, usando a biblioteca `pytest`. O objetivo é testar as funcionalidades de uma classe `Funcionario` que representa um funcionário, com métodos para calcular idade, sobrenome, bônus e outros atributos.

## Estrutura de Diretórios

- **codigo**: Contém o código-fonte principal do projeto.
  - `bytebank.py`: Implementação da classe `Funcionario`.
  - `coverage_relatorio_html`: Diretório para relatórios de cobertura de código gerados pelo `pytest-cov`.
  
- **tests**: Contém os testes para o código principal.
  - `test_bytebank.py`: Arquivo com os testes unitários para a classe `Funcionario`.

- **venv**: Ambiente virtual do Python para o projeto, onde estão instaladas as dependências.

- Arquivos de configuração:
  - `.coverage` e `.coveragerc`: Configurações para relatórios de cobertura.
  - `pytest.ini`: Configuração do pytest.
  - `requirements.txt`: Lista de dependências do projeto.
  
## Classe Funcionario

A classe `Funcionario` é uma representação de um funcionário com os seguintes atributos e métodos:

- `__init__`: Inicializa um funcionário com nome, data de nascimento e salário.
- `idade()`: Calcula a idade com base na data de nascimento.
- `sobrenome()`: Retorna o sobrenome do funcionário.
- `_eh_socio()`: Verifica se o funcionário é sócio (baseado em sobrenome e salário).
- `decrescimo_salario()`: Aplica um desconto de 10% no salário se o funcionário for sócio.
- `calcular_bonus()`: Calcula o bônus como 10% do salário, com exceção para salários muito altos.
- `__str__()`: Retorna uma representação em string do funcionário.

## Testes

Os testes estão no arquivo `test_bytebank.py` e cobrem as principais funcionalidades da classe `Funcionario`. Os principais testes incluem:

- `test_quando_idade_recebe_13_03_2000_deve_retornar_24`: Verifica se o cálculo da idade está correto.
- `test_quando_sobrenome_recebe_Lucas_Carvalho_deve_retornar_Carvalho`: Verifica se o sobrenome está correto.
- `test_quando_decrescimo_salario_recebe_100000_deve_retornar_90000`: Verifica o desconto no salário para sócios.
- `test_quando_calcular_bonus_recebe_1000_deve_retornar_100`: Testa o cálculo de bônus para salário de 1000.
- `test_quando_calcular_bonus_recebe_100000000_deve_retornar_exception`: Verifica se é lançada uma exceção para salários altos.

## Configuração e Instalação

1. **Clone o repositório**:
   ```bash
   git clone git@github.com:PedroTomasini/pytest-tdd.git
   cd pytest-tdd
   ```

2. **Crie e ative o ambiente virtual**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

3. **Instale as dependências**:
   ```bash
   pip install -r requirements.txt
   ```

## Executando os Testes

Para rodar todos os testes, utilize o comando:

```bash
pytest
```

Para gerar um relatório de cobertura, execute:

```bash
pytest --cov=codigo --cov-report=html
```

O relatório será gerado no diretório `coverage_relatorio_html`.

## Observações

- **Python 3.12.0** é usado neste projeto.
- **pytest** é utilizado para execução dos testes e geração de relatórios de cobertura.
