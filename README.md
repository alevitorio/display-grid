# 🌐 CSS Grid: Layouts Modernos com Estilo!

O `CSS Grid` é uma ferramenta poderosa para montar **layouts com linhas e colunas**, como se você estivesse desenhando o esqueleto da página. Ele permite **posicionar elementos com precisão** e criar áreas nomeadas de forma intuitiva. 💡

> Imagine uma folha quadriculada onde cada elemento do site se encaixa exatamente onde você quiser. Isso é o CSS Grid! 🧩

---

## 🎯 Quando usar CSS Grid?

- Quando quiser dividir sua página em **áreas bem definidas** (como header, menu, conteúdo, footer…)
- Quando quiser **posicionar elementos** horizontal e verticalmente sem complicações
- Quando quiser **controle total sobre o layout**, mesmo em responsividade

---

## 🚀 Ativando o Grid

```css
.grid-container {
  display: grid;
}
```

Isso transforma qualquer container em um **sistema de grade**.

---

## 🧱 Criando colunas e linhas

### 🧭 `grid-template-columns` e `grid-template-rows`

```css
.grid-container {
  display: grid;
  grid-template-columns: 200px 1fr 100px;
  grid-template-rows: auto 1fr auto;
}
```

📌 Explicando:
- **Colunas**:
  - `200px`: largura fixa
  - `1fr`: fração do espaço restante
  - `100px`: largura fixa
- **Linhas**:
  - `auto`: altura conforme o conteúdo
  - `1fr`: ocupa o que sobrar
  - `auto`: mesma ideia

---

## ✨ Exemplo básico com 4 caixinhas

### 📦 HTML

```html
<div class="grid-container">
  <div>1️⃣</div>
  <div>2️⃣</div>
  <div>3️⃣</div>
  <div>4️⃣</div>
</div>
```

### 🎨 CSS

```css
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}
```

🎯 Resultado:
```
+-------+-------+
|   1   |   2   |
+-------+-------+
|   3   |   4   |
+-------+-------+
```

- `1fr 1fr`: duas colunas iguais
- `gap: 10px`: espaçamento entre os itens

---

## 🔁 Tornando o Grid responsivo com `repeat` e `auto-fit`

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 15px;
}
```

🧠 Aqui o número de colunas **se ajusta automaticamente** ao tamanho da tela!

---

## 🧭 Posicionamento com `grid-column` e `grid-row`

```css
.item-destaque {
  grid-column: 1 / 3; /* ocupa da coluna 1 até a 3 (duas colunas) */
  grid-row: 1 / 2;    /* ocupa a primeira linha */
}
```

---

## 🧱 Layout completo com Áreas Nomeadas

Essa abordagem deixa o CSS mais **semântico e organizado**, perfeito para projetos maiores! 🎯

### 📦 HTML

```html
<div class="grid-container">
  <header>Topo</header>
  <nav>Menu</nav>
  <main>Conteúdo</main>
  <aside>Extras</aside>
  <footer>Rodapé</footer>
</div>
```

### 🎨 CSS

```css
.grid-container {
  display: grid;
  grid-template-areas:
    "header header"
    "menu   main"
    "menu   aside"
    "footer footer";
  grid-template-columns: 200px 1fr;
  grid-template-rows: auto 1fr 1fr auto;
  gap: 10px;
  height: 100vh;
}

/* Aplicando as áreas */
header { grid-area: header; background: #ccc; }
nav    { grid-area: menu;   background: #eee; }
main   { grid-area: main;   background: #ddd; }
aside  { grid-area: aside;  background: #f9f9f9; }
footer { grid-area: footer; background: #bbb; }
```

### 🔍 Visualmente, o layout é:

```
+----------------------+------------------------+
|       header         |        header          |
+----------------------+------------------------+
|        menu          |         main           |
+----------------------+------------------------+
|        menu          |         aside          |
+----------------------+------------------------+
|       footer         |        footer          |
+----------------------+------------------------+
```

---

## 📱 Layout Responsivo com Media Query

```css
@media (max-width: 768px) {
  .grid-container {
    grid-template-areas:
      "header"
      "menu"
      "main"
      "aside"
      "footer";
    grid-template-columns: 1fr;
  }
}
```

🪄 Com isso, o layout se adapta ao celular, empilhando as seções!

---

## 🧮 Tabela de propriedades úteis do CSS Grid

Claro! Aqui está uma **tabela com exemplos práticos das propriedades mais úteis do CSS Grid**, para facilitar o entendimento:

| **Propriedade**        | **Descrição**                                                    | **Exemplo**                                       |
|------------------------|------------------------------------------------------------------|---------------------------------------------------|
| `display: grid`        | Define um container como Grid                                   | `display: grid;`                                  |
| `grid-template-columns`| Define as colunas do grid                                        | `grid-template-columns: 1fr 2fr;`                 |
| `grid-template-rows`   | Define as linhas do grid                                         | `grid-template-rows: 100px auto;`                |
| `grid-column-gap`      | Espaço entre colunas                                             | `grid-column-gap: 20px;`                          |
| `grid-row-gap`         | Espaço entre linhas                                              | `grid-row-gap: 10px;`                             |
| `gap`                  | Atalho para `row-gap` e `column-gap`                            | `gap: 10px 20px;`                                 |
| `grid-template-areas`  | Define áreas nomeadas no layout                                  | `grid-template-areas: "header header" "main sidebar";` |
| `grid-area`            | Atribui um item a uma área nomeada                              | `grid-area: header;`                              |
| `grid-column`          | Define início/fim da coluna para um item                        | `grid-column: 1 / 3;`                             |
| `grid-row`             | Define início/fim da linha para um item                         | `grid-row: 2 / 4;`                                |
| `justify-items`        | Alinhamento horizontal dos itens dentro das células             | `justify-items: center;`                          |
| `align-items`          | Alinhamento vertical dos itens dentro das células               | `align-items: stretch;`                           |
| `justify-content`      | Alinha o grid dentro do container na horizontal                 | `justify-content: space-between;`                 |
| `align-content`        | Alinha o grid dentro do container na vertical                   | `align-content: center;`                          |
| `repeat()`             | Função para repetir colunas ou linhas                           | `grid-template-columns: repeat(3, 1fr);`          |
| `minmax()`             | Define valor mínimo e máximo para colunas/linhas                | `grid-template-columns: minmax(100px, 1fr);`      |
| `auto-fit / auto-fill` | Ajusta o número de colunas automaticamente                      | `grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));` |

---

## 📘 Boas práticas

✅ Use `grid-template-areas` para projetos maiores → o layout fica muito mais **visual e compreensível**  
✅ Combine Grid com `media queries` para **layouts responsivos**  
✅ Use `gap` para evitar usar margens internas que bagunçam o layout  
✅ Lembre-se que **cada filho direto** do container Grid se torna um item na grade!

---


Use `grid-template-areas`, `grid-column`, `grid-row` e `gap`. Tente também aplicar responsividade com media queries! 🚀

---

👨‍🏫 *Material criado para alunos de Desenvolvimento Web – CSS Grid do básico ao avançado, com contexto real e didático!*
