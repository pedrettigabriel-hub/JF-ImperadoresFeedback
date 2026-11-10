# Imperadores · Sistema de Feedbacks

Site onde cada atleta abre o próprio painel e vê os feedbacks e os drills em vídeo.

Os dados ficam numa **planilha do Google**: o treinador edita a planilha e todo mundo vê no site, em qualquer celular ou computador.

A planilha atual se chama **Imperadores · Feedbacks**, fica no Google Drive do treinador, e o link dela já está no `index.html`. Os passos 1 e 2 abaixo só servem se um dia for preciso trocar de planilha.

---

## 1. Criar a planilha

1. Abra o [Google Planilhas](https://sheets.google.com) e crie uma **planilha em branco**.
2. Importe os três modelos da pasta `modelo-planilha`. Para cada arquivo (`Atletas.csv`, `Feedbacks.csv`, `Drills.csv`):
   - **Arquivo → Importar → Fazer upload** e escolha o arquivo.
   - Em *Local de importação*, escolha **Inserir nova(s) página(s)** e clique em **Importar dados**.
3. Confira se as abas se chamam **exatamente** `Atletas`, `Feedbacks` e `Drills` (clique duas vezes no nome da aba para renomear). Depois apague a aba vazia `Página1`.
4. Clique em **Compartilhar → Acesso geral → Qualquer pessoa com o link → Leitor** e depois em **Concluído**.

### Colunas de cada aba

A primeira linha de cada aba é o cabeçalho. Não mude esses nomes.

| Aba | Colunas |
|---|---|
| **Atletas** | `Nome` |
| **Feedbacks** | `Atleta` · `Data` · `Categoria` · `Treinador` · `Título` · `Texto` |
| **Drills** | `Atleta` · `Título` · `Link` |

- **Atleta** precisa ser o mesmo nome da aba Atletas. Maiúsculas e acentos não importam.
- **Categoria** pode ser `Positivo`, `A melhorar` ou `Destaque`.
- **Link** pode ser do YouTube (vídeo normal ou Shorts) ou do Instagram (post ou Reels).
- Para um drill aparecer para **o time todo**, escreva `Todos` na coluna Atleta.

### Dica: listas de opções para evitar erro de digitação

Na aba **Feedbacks**:

- Selecione a coluna **A** (Atleta) → **Dados → Validação de dados → Adicionar regra** → *Menu suspenso (de um intervalo)* → digite `Atletas!A2:A` → **Concluído**.
- Selecione a coluna **C** (Categoria) → **Dados → Validação de dados → Adicionar regra** → *Menu suspenso* → opções `Positivo`, `A melhorar` e `Destaque` → **Concluído**.

Repita a primeira regra na coluna A da aba **Drills**.

---

## 2. Conectar o site à planilha

1. Com a planilha aberta, copie o link da **barra de endereço**. Ele começa com `https://docs.google.com/spreadsheets/d/...`.
2. Abra o `index.html` e cole esse link nesta linha, perto do começo do código:

   ```js
   const PLANILHA = 'COLE_AQUI_O_LINK_DA_PLANILHA';
   ```

---

## 3. Publicar no GitHub Pages

1. Suba o `index.html` e o `logo.png` para o repositório.
2. No GitHub, vá em **Settings → Pages**.
3. Em *Source*, escolha **Deploy from a branch**, depois a branch `main` e a pasta `/ (root)`, e clique em **Save**.
4. Em cerca de um minuto, o site estará em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

---

## No dia a dia

- **Novo feedback:** adicione uma linha na aba Feedbacks.
- **Novo drill:** adicione uma linha na aba Drills.
- **Novo atleta:** adicione o nome na aba Atletas.
- **Corrigir ou apagar:** edite ou apague a linha na planilha.
- Os atletas veem as mudanças quando abrem ou recarregam o site.
- Para outros treinadores também poderem editar, compartilhe a planilha com eles como **Editor**.

## ⚠️ Privacidade

Tudo o que está na planilha fica visível para qualquer pessoa que tenha o link do site. Qualquer atleta também consegue abrir o painel dos outros. Não escreva nada que não possa ser lido pelo time todo.
