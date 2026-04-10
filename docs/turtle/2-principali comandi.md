---
title: Principali comandi
layout: default
nav_order: 2
parent: Turtle
---

## Comandi base di Python

| Comando | A cosa serve | Esempio |
|---|---|---|
| `print()` | Mostra un messaggio | `print("Ciao")` |
| `input()` | Chiede un valore all'utente | `nome = input("Come ti chiami? ")` |
| `int()` | Converte un testo in numero intero | `eta = int(input("Età: "))` |
| `str()` | Converte in testo | `str(15)` |
| `for` | Ripete un blocco di istruzioni | `for i in range(4):` |
| `range()` | Genera una sequenza di numeri | `range(4)` |
| `if` | Esegue istruzioni solo se una condizione è vera | `if eta >= 18:` |

## Comandi base di Turtle

| Comando | A cosa serve | Esempio |
|---|---|---|
| `import turtle` | Importa il modulo | `import turtle` |
| `turtle.Turtle()` | Crea la tartaruga | `t = turtle.Turtle()` |
| `forward()` | Va avanti | `t.forward(100)` |
| `backward()` | Va indietro | `t.backward(50)` |
| `left()` | Ruota a sinistra | `t.left(90)` |
| `right()` | Ruota a destra | `t.right(90)` |
| `penup()` | Alza la penna | `t.penup()` |
| `pendown()` | Abbassa la penna | `t.pendown()` |
| `goto()` | Va in un punto preciso | `t.goto(100, 50)` |
| `circle()` | Disegna un cerchio | `t.circle(40)` |
| `color()` | Cambia colore | `t.color("red")` |
| `pensize()` | Cambia spessore della linea | `t.pensize(3)` |
| `speed()` | Cambia velocità | `t.speed(5)` |
| `hideturtle()` | Nasconde la tartaruga | `t.hideturtle()` |
| `turtle.done()` | Mantiene aperta la finestra | `turtle.done()` |

---