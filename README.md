# 🌎 WAR Estruturado: O Guia do Comandante (C Edition)

Bem-vindo ao **Desafio WAR**. Este projeto é um simulador de estratégia militar projetado para levar você do nível "escritor de scripts" ao nível "arquiteto de sistemas" em linguagem C. Aqui, o campo de batalha é a memória do computador.

---

## 🎖️ A Jornada de Evolução

O projeto é dividido em três fases que espelham o crescimento de um desenvolvedor profissional:

### 1. Nível Novato: O Quartel-General (Organização de Dados)
Nesta fase, o objetivo é parar de usar variáveis soltas e começar a usar **Estruturas**.
* **O Conceito:** Em vez de ter três vetores diferentes para nomes, cores e tropas, usamos uma `struct Territorio`. Isso cria um "objeto" que contém todas as informações de um território em um único bloco.
* **Ferramenta Técnica:** Vetores estáticos. É a forma mais segura de começar, onde o tamanho da memória é definido antes mesmo do programa rodar.

### 2. Nível Aventureiro: Logística Avançada (Gestão de Memória)
Aqui o jogo fica sério. Você sai do conforto do vetor fixo e entra no mundo da **Alocação Dinâmica**.
* **O Desafio:** Usar `calloc` para pedir memória ao sistema operacional durante a execução. 
* **Diferencial Didático:** Ao contrário do `malloc`, o `calloc` limpa a memória (coloca tudo em zero), evitando o famoso "lixo de memória" que causa bugs bizarros em jogos.
* **A Lógica do Combate:** Implementação do `rand()`. Você aprenderá a criar algoritmos de probabilidade onde o atacante e o defensor disputam valores aleatórios.



### 3. Nível Mestre: Estado-Maior (Arquitetura e Limpeza)
O código funciona, mas ele é elegante? No nível mestre, o foco é **Modularização**.
* **O Conceito:** O seu `main()` deve ser apenas um maestro. Toda a lógica pesada (atacar, verificar missão, imprimir mapa) deve estar em funções separadas.
* **Boas Práticas:** Uso de `const` para proteger dados que não devem ser alterados e passagem de parâmetros por **referência (ponteiros)** para ganhar performance, evitando cópias desnecessárias de dados na memória.

---

## 🛠️ Arsenal Tecnológico

| Recurso | Nível | Utilidade no Jogo |
| :--- | :--- | :--- |
| `struct` | Novato | Agrupar RG, Nome e Tropas do território. |
| `fgets` | Novato | Ler nomes com espaços sem quebrar o programa. |
| `calloc` | Aventureiro | Criar o mapa dinamicamente na memória RAM. |
| `srand(time(NULL))` | Aventureiro | Garantir que os dados da batalha sejam diferentes a cada rodada. |
| `Modularização` | Mestre | Tornar o código fácil de ler, testar e expandir. |

---

## 🧠 Dicas de Ouro para o Comandante

1.  **Cuidado com o Buffer:** Ao usar `scanf` seguido de `fgets`, o "Enter" pode ficar sobrando no teclado e pular a leitura do nome. Use um espaço antes do `%c` ou limpe o buffer.
2.  **Não esqueça o `free()`:** No nível Aventureiro e Mestre, toda memória que você pediu com `calloc` deve ser devolvida com `free` ao final do programa. Memória esquecida é território perdido (Memory Leak)!
3.  **Lógica de Missão:** Ao verificar se o exército Verde foi destruído, você precisará percorrer todo o seu vetor de structs e checar a cor e a quantidade de tropas.

---
*Desenvolvido para a trilha de Engenharia de Software - MateCheck.*
