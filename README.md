O Java passa por várias etapas desde a escrita do código até a execução no computador.

## 1. Código-fonte (.java)

É o arquivo que o programador escreve usando a linguagem Java.

Exemplo:

```java
public class OlaMundo {
    public static void main(String[] args) {
        System.out.println("Olá, Mundo!");
    }
}
```

Esse arquivo é chamado de **código-fonte** e possui a extensão **.java**.

---

## 2. JDK (Java Development Kit)

O **JDK** é o pacote usado para **desenvolver programas Java**.

Ele contém:

* Compilador (`javac`)
* JVM
* JRE
* Bibliotecas do Java
* Ferramentas para desenvolvimento (debug, documentação, etc.)

Sem o JDK você **não consegue criar nem compilar** programas Java.

### O compilador (`javac`)

Quando você executa:

```bash
javac OlaMundo.java
```

O compilador transforma o código-fonte em **bytecode**.

---

## 3. Bytecode (.class)

Depois da compilação, é criado um arquivo:

```
OlaMundo.class
```

Esse arquivo contém o **bytecode**.

### O que é bytecode?

É uma linguagem intermediária.

* Não é o código Java.
* Não é linguagem de máquina.
* É um código que a JVM consegue entender.

Pense assim:

```
Português (Java)
        ↓ traduz
Inglês (Bytecode)
        ↓ interpreta
Idioma do computador
```

Por isso um programa Java pode funcionar em vários sistemas operacionais.

---

## 4. JVM (Java Virtual Machine)

A **JVM** é a Máquina Virtual Java.

Sua função é:

* Ler o bytecode (.class)
* Transformá-lo em linguagem de máquina
* Executar o programa

É a JVM que realmente faz o programa funcionar.

Ela também é responsável por:

* gerenciamento de memória;
* execução do código;
* coleta de lixo (Garbage Collector);
* segurança.

---

## 5. JRE (Java Runtime Environment)

O **JRE** é o ambiente necessário para **executar** programas Java.

Ele contém:

* JVM
* Bibliotecas necessárias para execução

O JRE **não possui o compilador (`javac`)**, então ele não consegue criar programas, apenas executá-los.

---

# Fluxo completo

```text
Programador
     │
     ▼
Código Java (.java)
     │
     │ javac (Compilador)
     ▼
Bytecode (.class)
     │
     │ JVM
     ▼
Código de Máquina
     │
     ▼
Programa executando
```

---

# Relação entre JDK, JRE e JVM

```text
JDK
│
├── Compilador (javac)
├── Ferramentas
└── JRE
      │
      ├── JVM
      └── Bibliotecas Java
```

Observe que:

* **JDK** é o pacote completo para desenvolvimento.
* **JRE** faz parte do JDK e serve para executar programas.
* **JVM** faz parte do JRE e executa o bytecode.

---

# Exemplo passo a passo

Suponha que você escreveu:

```java
public class Soma {
    public static void main(String[] args) {
        int a = 5;
        int b = 3;
        System.out.println(a + b);
    }
}
```

### Passo 1

Você salva:

```
Soma.java
```

↓

### Passo 2

Compila:

```bash
javac Soma.java
```

↓

É criado:

```
Soma.class
```

↓

### Passo 3

Executa:

```bash
java Soma
```

O comando `java` chama a JVM.

↓

### Passo 4

A JVM lê o bytecode.

↓

### Passo 5

A JVM transforma o bytecode em instruções que o processador entende.

↓

### Passo 6

O programa imprime:

```
8
```

---

# Por que Java é multiplataforma?

Outras linguagens geralmente compilam diretamente para o sistema operacional.

Exemplo:

```
C
↓
Windows
```

Se quiser executar no Linux, é preciso recompilar.

Já no Java:

```text
Código Java
      │
      ▼
Bytecode
      │
 ┌────┴────┐
 ▼         ▼
JVM      JVM
Windows  Linux
```

O mesmo arquivo `.class` pode ser executado em qualquer sistema que tenha uma JVM compatível. Por isso o Java segue o princípio **"Write Once, Run Anywhere" (Escreva uma vez, execute em qualquer lugar).**

---

# Resumo

| Componente               | Função                                                                                     |
| ------------------------ | ------------------------------------------------------------------------------------------ |
| **Código-fonte (.java)** | Arquivo escrito pelo programador.                                                          |
| **JDK**                  | Kit de desenvolvimento. Contém o compilador (`javac`), o JRE e ferramentas para programar. |
| **Compilador (`javac`)** | Converte o código Java em bytecode (`.class`).                                             |
| **Bytecode (.class)**    | Código intermediário que pode ser executado em qualquer plataforma com uma JVM.            |
| **JRE**                  | Ambiente de execução. Contém a JVM e as bibliotecas necessárias para rodar programas Java. |
| **JVM**                  | Lê o bytecode, converte para código de máquina e executa o programa.                       |

### Esquema final

```text
        Código Java (.java)
               │
               │  javac (JDK)
               ▼
        Bytecode (.class)
               │
               │  JVM (dentro do JRE)
               ▼
      Código de Máquina
               │
               ▼
      Programa em execução
```

Essa é a sequência completa do funcionamento do Java: **você escreve o código-fonte → o JDK o compila em bytecode → a JVM interpreta ou compila esse bytecode para código de máquina → o computador executa o programa.**
