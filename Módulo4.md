## ☕ Módulo 4 (Java): O Hacker da Heap

> [!NOTE]
> **Conceito:** Em Java não existem ponteiros diretos para a memória RAM por questões de segurança. Em vez disso, usas **Referências de Objetos**. A memória *Heap* é onde os teus objetos vivem, e as tuas variáveis guardam apenas a "morada" (referência) de onde esse objeto está!

```text
 ┌─────────────────────────────────────────────────────────┐
 │               MEMÓRIA HEAP (OBJETOS JAVA)               │
 ├───────────────────┬───────────────────┬─────────────────┤
 │ Referência        │ Objeto Conectado  │ Atributos       │
 ├───────────────────┼───────────────────┼─────────────────┤
 │ alvoAtual ───────┼──> [ CofreB ]     │ valor = 5000    │
 │ (Referência)      │                   │ trancado = true │
 └───────────────────┴───────────────────┴─────────────────┘
```
🎯 Qual é o Objetivo Deste Jogo?
Neste exercício, assumes o papel de um hacker que opera um terminal de controlo de objetos em Java.

O Teu Papel: Investigar como as variáveis do tipo objeto em Java funcionam por referência.

A Tua Missão: Usar uma única variável de referência (alvoAtual) para saltar de objeto em objeto dentro da memória Heap.

O Desafio Final: Invocar métodos de hacking para alterar os valores dos cofres e desativar os seus sistemas de segurança sem instanciar novos objetos!

📌 Tópicos
🏛️ Classes e Objetos: Criar moldes (class) e instanciá-los (new).

🔗 Referências na Heap: Entender a diferença entre guardar valores primitivos e moradas de objetos.

🔒 Encapsulamento & Métodos: Alterar o estado de um objeto de forma controlada.

🚫 Referência Nula (null): Tratar exceções do tipo NullPointerException.
