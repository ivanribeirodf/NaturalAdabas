# Projeto Natural/Adabas

Este projeto tem como objetivo a prática e o estudo dos principais comandos da linguagem **Natural** em conjunto com o banco de dados **Adabas**, utilizando instruções básicas e intermediárias para manipulação de dados, estruturas condicionais e formatação de strings.

## 🛠 Funcionalidades Implementadas

### 🔹 Atribuições
- `MOVE` e `:=` utilizados para atribuição de valores entre variáveis.
- Utilização da variável de sistema `*DATX` para obter a **data atual**.

### 🔹 Operações Aritméticas
- `ADD`: utilizado para somar valores a uma variável (ex: adicionar 7 dias à data).
- `COMPUTE`: para realizar cálculos aritméticos ou atribuições diretas.
- `ROUNDED`: utilizado para **arredondar** o resultado de cálculos, como:
  ```natural
  COMPUTE NOVO-SALARIO = SALARIO * 1.15087 ROUNDED
  ```

### 🔹 Conversão e Formatação
- `MOVE EDITED`: move e converte variáveis aplicando **máscaras de edição**.

### 🔹 Estruturas Condicionais
- `DECIDE`: estrutura semelhante ao `IF/ELSE`, utilizada para verificar múltiplas condições de forma organizada.

### 🔹 Strings e Manipulação de Texto
- `DYNAMIC`: define variáveis com **tamanho dinâmico**, sem necessidade de declaração fixa.
- `COMPRESS`: junta várias strings ou variáveis em uma só.
  - Exemplo:
    ```natural
    COMPRESS NOME SOBRENOME INTO NOME-COMPLETO
    ```
- `WITH DELIMITER`: permite inserir um delimitador entre os elementos concatenados.
  - Exemplo:
    ```natural
    COMPRESS NOME SOBRENOME INTO NOME-COMPLETO WITH DELIMITER '-'
    ```
- `SEPARATE`: separa o conteúdo de uma variável em partes, armazenando-as em elementos de um array.
  - Exemplo:
    ```natural
    SEPARATE NOME-COMPLETO INTO ARRAY-NOMES(*) WITH DELIMITER ' '
    ```

## 💡 Exemplos de Código

```natural
/* Obter data atual
MOVE *DATX TO DATA-HOJE

/* Somar dias
ADD 7 TO DATA-HOJE

/* Calcular novo salário
COMPUTE NOVO-SALARIO = SALARIO * 1.15087 ROUNDED

/* Formatar com edição
MOVE EDITED SALARIO TO SALARIO-FORMATADO

/* Verificação com DECIDE
DECIDE ON FIRST VALUE DEPARTAMENTO
  VALUE 'RH'    DISPLAY 'Recursos Humanos'
  VALUE 'TI'    DISPLAY 'Tecnologia'
  NONE VALUE    DISPLAY 'Departamento desconhecido'
END-DECIDE

/* Manipular nomes
COMPRESS PRIMEIRO-NOME SOBRENOME INTO NOME-COMPLETO WITH DELIMITER ' '

SEPARATE NOME-COMPLETO INTO ARRAY-NOMES(*) WITH DELIMITER ' '
```

## ✅ Objetivos Concluídos

- [x] Atribuições e variáveis de sistema  
- [x] Operações aritméticas com `ADD`, `COMPUTE` e `ROUNDED`  
- [x] Conversão com `MOVE EDITED`  
- [x] Estruturas de decisão com `DECIDE`  
- [x] Manipulação de strings com `COMPRESS`, `WITH DELIMITER` e `SEPARATE`  
- [x] Uso de arrays e variáveis dinâmicas  

## 📌 Próximos Passos

- Incluir loops (`FOR`, `REPEAT`, `ESCAPE TOP/BOTTOM`)
- Iniciar integração com base de dados Adabas (Ler, Atualizar, Gravar, Deletar)
- Trabalhar com subprogramas e módulos reutilizáveis
- Criar pequenos relatórios de saída formatada

## 📎 Requisitos

- Natural One (ou ambiente mainframe com Natural)
- Banco de dados Adabas

## 📝 Licença

Projeto de uso pessoal e educacional.
