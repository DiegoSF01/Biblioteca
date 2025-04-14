# Arquitetura MVC (Model-View-Controller)

## 📌 O que é MVC?

**MVC** (Model-View-Controller) é um padrão de arquitetura de software que separa a aplicação em três componentes principais:

- **Model (Modelo)**
- **View (Visão)**
- **Controller (Controlador)**

Essa separação facilita a manutenção, reutilização de código e organização da aplicação.

---

## 🧩 Componentes do MVC

### 🧠 Model (Modelo)

Responsável pela **lógica de negócio** e **manipulação dos dados** da aplicação. Ele acessa o banco de dados, processa regras de negócio e retorna os dados solicitados.

**Exemplo de responsabilidade:**
- Consultar usuários no banco de dados.
- Validar regras como "idade mínima para cadastro".

```python
# Exemplo simples em Python
class UsuarioModel:
    def __init__(self, nome, idade):
        self.nome = nome
        self.idade = idade

    def salvar(self):
        # Lógica para salvar o usuário no banco de dados
        pass
```

---

### 🖼️ View (Visão)

Responsável pela **interface com o usuário**. Exibe os dados fornecidos pelo Model e envia interações do usuário para o Controller.

**Exemplo de responsabilidade:**
- Mostrar um formulário de cadastro.
- Exibir uma lista de produtos.

```html
<!-- Exemplo de View em HTML -->
<h1>Bem-vindo, {{ usuario.nome }}</h1>
```

---

### 🎮 Controller (Controlador)

Responsável por **intermediar a View e o Model**. Ele recebe as ações do usuário (como cliques ou envios de formulário), processa essas ações com ajuda do Model e decide qual View será exibida.

**Exemplo de responsabilidade:**
- Receber os dados de um formulário e salvar no banco.
- Decidir qual página será exibida após uma ação.

```python
class UsuarioController:
    def cadastrar_usuario(nome, idade):
        usuario = UsuarioModel(nome, idade)
        usuario.salvar()
        return render_template("sucesso.html", usuario=usuario)
```

---

## 🔁 Fluxo de Dados no MVC

1. O usuário interage com a **View**.
2. A **View** envia uma requisição ao **Controller**.
3. O **Controller** processa a ação usando o **Model**.
4. O **Model** retorna dados ao **Controller**.
5. O **Controller** envia os dados para a **View**, que os exibe ao usuário.

---

## ✅ Benefícios do MVC

- **Separação de responsabilidades**
- **Facilidade para manutenção**
- **Melhor organização do código**
- **Reutilização de componentes**
- **Facilidade para trabalhar em equipe (front e back separados)**

---

## 🛠️ Exemplos de Frameworks que usam MVC

- **Django** (Python)
- **Ruby on Rails** (Ruby)
- **Laravel** (PHP)
- **ASP.NET MVC** (C#)
- **Spring MVC** (Java)
