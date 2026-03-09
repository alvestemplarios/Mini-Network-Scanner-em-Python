# 🛰️ Mini Network Scanner em Python

Projeto simples de **Scanner de Portas** desenvolvido em Python para fins educacionais.

O programa verifica portas comuns em um host para identificar quais serviços podem estar ativos.

Este tipo de ferramenta é usado em **administração de redes e segurança da informação**.

---

## 📌 Objetivo

Este projeto foi criado para praticar:

* Programação em Python
* Conceitos de redes de computadores
* Segurança da informação
* Uso de sockets
* Automação de tarefas de rede

---

## ⚙️ Tecnologias utilizadas

* Python 3
* Biblioteca `socket`

---

## 📂 Estrutura do Projeto

```
network-scanner-python
│
├── scanner.py
└── README.md
```

---

## 💻 Código do Scanner

```python
import socket

print("=== MINI NETWORK SCANNER ===")

alvo = input("Digite o IP ou domínio: ")

portas = [21,22,23,25,53,80,110,139,143,443]

print("\nEscaneando alvo:", alvo)

for porta in portas:
    cliente = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    cliente.settimeout(1)

    resultado = cliente.connect_ex((alvo, porta))

    if resultado == 0:
        print(f"Porta {porta} ABERTA")

    cliente.close()
```

---

## ▶️ Como Executar

Clone o repositório:

```
git clone https://github.com/SEU-USUARIO/network-scanner-python.git
```

Entre na pasta:

```
cd network-scanner-python
```

Execute o programa:

```
python scanner.py
```

---

## 📊 Exemplo de execução

```
=== MINI NETWORK SCANNER ===

Digite o IP ou domínio: scanme.nmap.org

Escaneando alvo...

Porta 22 ABERTA
Porta 80 ABERTA
Porta 443 ABERTA
```

---

## 🔎 Portas analisadas

O scanner verifica algumas portas comuns:

* 21 → FTP
* 22 → SSH
* 23 → Telnet
* 25 → SMTP
* 53 → DNS
* 80 → HTTP
* 110 → POP3
* 139 → NetBIOS
* 143 → IMAP
* 443 → HTTPS

---

## ⚠️ Aviso

Este projeto foi criado **apenas para fins educacionais**.

Não utilize scanners em redes ou sistemas sem autorização.

---

## 👨‍💻 Autor

**Alves**

Estudante de redes de computadores e segurança da informação.
