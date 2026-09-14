# Caixa Eletrônico

Sistema de simulação de um caixa eletrônico (ATM) desenvolvido em **Java**, com interface gráfica feita em **Swing**. O projeto permite efetuar saques, consultar saldo disponível, repor cédulas e configurar uma cota mínima de segurança para o caixa.

## Funcionalidades

### Módulo do Cliente
- **Efetuar Saque**: realiza o saque de um valor informado, calculando automaticamente a melhor combinação de cédulas disponíveis para entregar ao usuário.

### Módulo do Administrador
- **Relatório de Cédulas**: exibe a quantidade disponível de cada tipo de nota (R$ 100, 50, 20, 10, 5 e 2).
- **Valor Total Disponível**: mostra o valor total em dinheiro que o caixa possui no momento.
- **Reposição de Cédulas**: permite adicionar uma quantidade de notas de um valor específico ao estoque do caixa.
- **Cota Mínima**: define um valor de reserva de segurança; se o caixa atingir esse valor ou menos, ele para de realizar saques.

### Módulo Geral
- **Sair**: encerra a aplicação.

## Regras de negócio do saque

- O caixa não realiza saques se o valor total disponível estiver igual ou abaixo da cota mínima configurada.
- Valores de R$ 1 ou R$ 3 (ou valores menores/iguais a zero) não são aceitos, pois não é possível formá-los com as cédulas disponíveis (R$ 100, 50, 20, 10, 5 e 2).
- O sistema tenta priorizar notas de maior valor (100 e 50) e ajusta a combinação até encontrar uma forma exata de entregar o valor pedido, dentro das cédulas em estoque.
- Existe um limite de **30 cédulas por saque**; se a única combinação possível ultrapassar esse limite, o saque é recusado.

## Estrutura do projeto

```
caixaeletronico/
├── ICaixaEletronico.java   # Interface com o contrato das operações do caixa
├── CaixaEletronico.java    # Implementação da lógica de negócio (saque, reposição, etc.)
├── GUI.java                # Interface gráfica (Swing) que consome a lógica
└── DICIONARIO DE DADOS COMPLETO.pdf  # Documentação de dados do projeto
```

## Tecnologias utilizadas

- Java
- Swing (interface gráfica)

## Como executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/caixaEletronico.git
   ```
2. Abra o projeto na sua IDE de preferência (ex: IntelliJ IDEA ou Eclipse).
3. Execute a classe `CaixaEletronico.java`, que contém o método `main` responsável por iniciar a lógica e abrir a interface gráfica.

## Interface

Ao iniciar, a aplicação abre uma janela simples dividida em três módulos (Cliente, Administrador e Geral), cada um com botões para as operações correspondentes. Todas as interações (valores de saque, reposição, cota mínima) são feitas por meio de caixas de diálogo (`JOptionPane`).

## Autor

Projeto acadêmico desenvolvido em Java.