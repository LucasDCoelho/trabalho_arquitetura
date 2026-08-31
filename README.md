# Missão Marte Unifor — Jogo OO em Console

**Disciplina:** Programação Orientada a Objetos  
**Repositório:** https://github.com/LucasDCoelho/trabalho_arquitetura

## Integrantes

| Nome | Matrícula | GitHub |
|---|---|---|
| Lucas Coelho | 2510461 | LucasDCoelho |
| João Pedro Carvalho | 2510547 | carvalho-jp |

## Sobre o Projeto

Jogo interativo em console onde o jogador pilota uma nave no mapa marciano, resgata passageiros (Professor, Engenheiro, Astronauta), desvia de asteroides e inimigos, e deve retornar à plataforma de pouso `(0,0)` para vencer. Aplica os pilares de OO: encapsulamento, herança, polimorfismo e composição.

## Estrutura

```
src/missao/
├── Main.java         — loop principal, menu e persistência
├── Missao.java       — composição: nave, passageiros, asteroides, inimigos
├── Nave.java         — posição, vidas, embarque, movimento
├── Passageiro.java   — classe base dos passageiros
├── Professor.java    — herda Passageiro (+10 pts)
├── Engenheiro.java   — herda Passageiro (+15 pts)
├── Astronauta.java   — herda Passageiro (+20 pts)
├── Asteroide.java    — obstáculo estático
├── Inimigo.java      — obstáculo com movimento aleatório
└── Dificuldade.java  — enum FACIL / MEDIO / DIFICIL
```

## Compilação e Execução

Execute os comandos abaixo a partir da raiz do repositório:

```bash
javac -encoding UTF-8 -d out src/missao/*.java
java -cp out missao.Main
```

> Requer JDK 8 ou superior.

## Como Jogar

| Comando | Ação |
|---|---|
| `w` | Mover para cima |
| `s` | Mover para baixo |
| `a` | Mover para a esquerda |
| `d` | Mover para a direita |
| `c` | Embarcar passageiro na posição atual |
| `q` | Sair / abortar missão |

- Cada movimento custa **1 ponto**
- Embarcar um passageiro vale **+10 a +20 pontos** (varia por tipo)
- Colidir com asteroide ou inimigo custa **1 vida** (total: 3 vidas)
- Após resgatar todos os passageiros, retorne a `(0,0)` para completar a missão
- O ranking Top 5 é salvo em `ranking.json`

## Geração de Javadoc

```bash
javadoc -d docs -encoding UTF-8 -charset UTF-8 -sourcepath src missao
```

Os arquivos HTML serão gerados em `docs/` (abra `docs/index.html`).
