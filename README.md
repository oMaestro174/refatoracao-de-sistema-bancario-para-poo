# Desafio: Refatoração de Sistema Bancário para POO

## 📖 Sobre o Projeto

Este projeto consiste na refatoração de um [sistema bancário simples](https://github.com/oMaestro174/otimizando-sistema-bancario-com-funcoes-em-python.git), originalmente desenvolvido com uma abordagem procedural em Python. O principal objetivo do desafio é aplicar os conceitos de **Programação Orientada a Objetos (POO)** para reestruturar o código, tornando-o mais modular, escalável e de fácil manutenção, seguindo um diagrama de classes UML pré-definido.

-----

## 🎯 O Desafio

O projeto foi dividido em duas etapas principais, conforme proposto:

1.  **Desafio 1: Modelagem das Classes**

      - Atualizar a implementação do sistema para armazenar os dados de clientes e contas bancárias em **objetos**, em vez de dicionários.
      - A nova estrutura de código deve seguir rigorosamente o modelo de classes UML fornecido, estabelecendo a base da arquitetura orientada a objetos.

2.  **Desafio Extra: Integração com o Menu**

      - Após a modelagem das classes, atualizar os métodos que tratam as opções do menu interativo.
      - O objetivo é fazer com que a interface do usuário (o menu `main`) utilize os novos objetos e seus respectivos métodos para realizar as operações de depósito, saque, criação de cliente, etc.

-----

## ✨ Principais Conceitos Aplicados

A solução deste desafio envolveu a aplicação de diversos pilares e conceitos da Programação Orientada a Objetos:

  - **Abstração:** Criação de uma classe abstrata `Transacao` para servir como um "contrato" para as classes `Saque` e `Deposito`.
  - **Encapsulamento:** Proteção dos atributos sensíveis das classes (como `_saldo`), expondo-os de forma controlada através de propriedades (`@property`).
  - **Herança:** Utilização de herança para criar especializações, como `PessoaFisica` que herda de `Cliente`, e `ContaCorrente` que herda de `Conta`, reaproveitando código e adicionando comportamentos específicos.
  - **Polimorfismo:** A capacidade de um objeto `Cliente` realizar uma `Transacao` sem precisar saber se ela é um `Saque` ou um `Deposito`, simplificando a lógica de operações.
  - **Separação de Responsabilidades:** O código foi dividido em duas camadas principais:
    1.  **Backend (Classes):** As classes (`Conta`, `Cliente`, etc.) contêm a lógica de negócio e as regras do sistema.
    2.  **Frontend (Funções do Menu):** Funções que servem como uma "ponte", traduzindo as interações do usuário em comandos para os objetos do backend.

-----

## 📂 Estrutura do Projeto

A evolução do código pode ser observada através das duas versões principais desenvolvidas:

  - `sistema_bancario_v1.py`: **(Desafio 1 Concluído)**

      - Contém apenas a definição de todas as classes, conforme o diagrama UML.
      - Representa a "biblioteca" ou o "backend" do sistema, com toda a lógica de negócio encapsulada nos objetos. Não possui um menu interativo funcional.

  - `sistema_bancario_v2.py`: **(Desafio Extra Concluído)**

      - Inclui todas as classes da V1.
      - Adiciona as funções de interface (`depositar`, `sacar`, `criar_cliente`, etc.) e a função `main()` com o loop principal do menu.
      - Esta é a versão final e funcional do sistema, que integra o backend orientado a objetos com a interface do usuário.

-----

## 🛠️ Tecnologias Utilizadas

  - **Python 3**
      - Módulo `abc` para criação de classes abstratas.
      - Módulo `datetime` para registrar a data das transações.
      - Módulo `textwrap` para formatação do menu.

-----

## 🚀 Como Executar

Para executar o sistema bancário completo, siga os passos abaixo:

1.  Certifique-se de ter o Python 3 instalado em sua máquina.
2.  Clone este repositório ou faça o download do arquivo [`sistema_bancario_v2.py`](sistema_bancario_v2.py).
3.  Abra um terminal na pasta onde o arquivo está localizado.
4.  Execute o seguinte comando:

<!-- end list -->

```bash
python sistema_bancario_v2.py
```

5.  O menu interativo será exibido no terminal e você poderá utilizar as funcionalidades do sistema.

-----

## 🕹️ Exemplo de Uso

```
    ================ MENU ================
    [d]     Depositar
    [s]     Sacar
    [e]     Extrato
    [nc]    Nova conta
    [lc]    Listar contas
    [nu]    Novo usuário
    [q]     Sair
    => nu

Informe o CPF (somente número): 12345678900
Informe o nome completo: Joao da Silva
Informe a data de nascimento (dd-mm-aaaa): 10-05-1985
Informe o endereço (logouro, nro - bairro - cidade/sigla estado): Rua Exemplo, 123 - Centro - Boa Vista/RR

=== Cliente criado com sucesso! ===

    ================ MENU ================
    [d]     Depositar
    [s]     Sacar
    ...
```



-----

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
