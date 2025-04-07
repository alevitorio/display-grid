# 🌐 Aprendendo CSS Grid com Estilo!

O `display: grid` é uma ferramenta **poderosa e moderna** do CSS para criar **layouts com colunas e linhas**, como se fosse uma planta baixa de um site 🏗️. Ideal para organizar a página em partes como cabeçalho, menu, conteúdo e rodapé com muita clareza!

---

## ✅ Quando usar CSS Grid?

Use quando quiser montar um layout com múltiplas colunas e linhas (como sites, dashboards, áreas administrativas etc). Ele permite que você defina **áreas nomeadas**, tamanhos fixos, proporcionais e muito mais! 🧠

---

## 🧱 Conceitos básicos

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
  grid-template-columns: 1fr 1fr; /* 2 colunas iguais */
  gap: 10px;
}
```

🔍 Explicando:
- `display: grid`: ativa o Grid no container;
- `1fr 1fr`: significa que as duas colunas terão o mesmo tamanho (1 fração do espaço total);
- `gap`: define o espaçamento entre os itens.

---

### 📏 Controlando colunas e linhas

```css
.grid-container {
  display: grid;
  grid-template-columns: 200px auto 100px;
}
```

⬆️ Aqui temos **3 colunas**:
- A 1ª com 200px fixos;
- A 2ª ocupa o restante do espaço;
- A 3ª com 100px fixos.

---

### 🌈 Posicionando itens com `grid-column` e `grid-row`

```css
.item-destaque {
  grid-column: 1 / 3; /* ocupa da coluna 1 até a 3 */
  grid-row: 1 / 2;    /* ocupa a primeira linha */
}
```

---

### 🔁 Layout responsivo com `repeat` e `auto-fit`

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 20px;
}
```

✨ Assim, o número de colunas se adapta ao tamanho da tela automaticamente!

---

## 🔲 Layout com Áreas Nomeadas (`grid-template-areas`)

Essa é uma das formas **mais organizadas** de montar um layout com Grid. Você pode **nomear** cada área da sua página!

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
    "header  header"
    "menu    main"
    "menu    aside"
    "footer  footer";
  grid-template-columns: 200px 1fr;
  grid-template-rows: auto 1fr 1fr auto;
  gap: 10px;
  height: 100vh;
}

header { grid-area: header; background: #ccc; }
nav    { grid-area: menu;   background: #eee; }
main   { grid-area: main;   background: #ddd; }
aside  { grid-area: aside;  background: #f0f0f0; }
footer { grid-area: footer; background: #bbb; }
```

### 👀 Visualização do Layout

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

## 📱 Deixando o layout responsivo

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

📲 Agora, em dispositivos móveis, o conteúdo será empilhado verticalmente!

---

## 🛠️ Tabela de propriedades importantes

| Propriedade             | Para que serve                                                                  |
|-------------------------|----------------------------------------------------------------------------------|
| `display: grid`         | Ativa o Grid Layout no container                                                |
| `grid-template-columns` | Define quantas colunas o layout terá e o tamanho de cada uma                    |
| `grid-template-rows`    | Define quantas linhas o layout terá e o tamanho de cada uma                     |
| `grid-template-areas`   | Nomeia as áreas do layout (muito útil pra deixar o CSS legível!)                |
| `grid-area`             | Informa em qual área o item ficará dentro do grid                               |
| `grid-column`           | Define em quais colunas o item deve ficar (início/fim)                          |
| `grid-row`              | Define em quais linhas o item deve ficar (início/fim)                           |
| `gap`                   | Espaço entre colunas e linhas                                                   |
| `justify-items`         | Alinha os itens horizontalmente dentro das células                             |
| `align-items`           | Alinha os itens verticalmente dentro das células                               |
| `place-items`           | Atalho para `align-items` e `justify-items` juntos                              |

---

## 💡 Dica final

> Com `grid-template-areas`, você **desenha o layout usando palavras**, o que deixa tudo mais organizado e fácil de entender! Ideal para projetos em grupo, códigos revisáveis e para manter a sanidade! 😄

---

## 🧪 Bora praticar?

Tente montar um layout com:

- Cabeçalho
- Menu lateral
- Conteúdo principal
- Área de propaganda (aside)
- Rodapé

Use `grid-template-areas` e combine com as outras propriedades do Grid!

---

👨‍🏫 *Material preparado para aula de Desenvolvimento Web – CSS Grid na prática!*
```

