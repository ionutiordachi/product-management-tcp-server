# TCP Client-Server — Text & Binary Protocol

Acesta este un proiect realizat în cadrul cursului de **Rețele de Calculatoare**, în care am implementat un sistem client-server TCP în Python, folosind două abordări de protocol: **text** și **binar**.

---

## Ce am făcut

Am construit două variante funcționale de comunicare client-server:

- **Text Protocol** — comenzile sunt trimise ca text simplu, răspunsurile sunt prefixate cu lungimea mesajului
- **Binary Protocol** — datele sunt serializate cu `pickle` și trimise ca bytes, tot cu prefix de lungime

Serverul menține un dicționar în memorie și suportă operații CRUD complete, cu gestionarea erorilor și suport pentru mai mulți clienți simultan prin **threading**.

---

## Comenzi suportate (Text Protocol)

| Comandă | Exemplu | Răspuns |
|---|---|---|
| `add` | `add mere 59` | `mere added` |
| `get` | `get mere` | `59` |
| `remove` | `remove mere` | `mere removed` |
| `list` | `list` | `DATA\|mere=59,pere=145` |
| `count` | `count` | `DATA 2` |
| `clear` | `clear` | `all data deleted` |
| `update` | `update mere 10` | `Data updated` |
| `pop` | `pop mere` | `Data 59` |
| `quit` | `quit` | `Goodbye` |

---

## Structura proiectului

```
proto-tcp/
├── text-proto-tcp/
│   ├── tcp-client.py
│   └── tcp-server.py
├── binary-proto-tcp/
│   ├── tcp-client.py
│   └── tcp-server.py
└── README.md
```

---

## Tehnologii folosite

- **Python 3** — limbajul de implementare
- **socket** — comunicare TCP
- **threading** — suport pentru clienți multipli simultan
- **pickle** — serializare binară (Binary Protocol)
- **io.BytesIO** — manipulare stream-uri binare

---

## Cum rulezi

**Serverul:**
```bash
python tcp-server.py
```

**Clientul** (într-un terminal separat):
```bash
python tcp-client.py
```

---
