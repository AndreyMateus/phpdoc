# PHPDoc Tags Cheat Sheet (HTML Interativo)

Um **cheat sheet interativo** em HTML para consultar as principais **tags do PHPDoc** de forma rápida e prática.

A ideia é simples: você abre a página no navegador, vê uma lista de tags (uma por linha) com **“Tag + onde usa”** e, ao clicar na linha, aparece **a descrição e um exemplo** logo abaixo.  
Também há uma **barra de busca** para filtrar por **nome da tag**, **onde usar** ou **descrição**.

> ✅ Este projeto foi criado com ajuda de **IA (Inteligência Artificial)** para acelerar a construção do layout, organização do conteúdo e implementação do filtro/busca.

---

## Observações importantes

- **PHPDoc não executa código**: ela não muda o comportamento do PHP em runtime.  
- PHPDoc funciona como **metadado**: informações extras escritas para **humanos e ferramentas**.
- Ela **ajuda diretamente as IDEs** (como VS Code e PhpStorm) a:
  - fornecer **autocomplete mais preciso**
  - inferir tipos de variáveis e retornos
  - identificar uso incorreto de métodos/propriedades
  - mostrar documentação inline ao passar o mouse
- PHPDoc também é usada por **analisadores estáticos** (PHPStan, Psalm) para:
  - detectar bugs antes da execução
  - validar contratos de métodos
  - simular **generics** e tipos avançados que o PHP não expressa nativamente
- Sempre que possível, prefira **tipagem nativa do PHP** (`int`, `string`, `User`, `: void`, etc.).
- Use PHPDoc quando:
  - o PHP **não consegue expressar o tipo completo** (ex.: `Book[]`)
  - você quer documentar **contrato**, **intenção**, **exceções** e **comportamento**
  - você trabalha com código grande, times, ou quer facilitar manutenção futura

👉 Pense no PHPDoc como uma **ponte entre o código, a IDE e quem vai ler o código no futuro**.

---

## Funcionalidades

- ✅ Lista de tags do PHPDoc com:
  - **Tag**
  - **Onde usar**
  - **Descrição**
  - **Exemplo**
- ✅ Clique para expandir/colapsar detalhes
- ✅ Barra de busca (busca por **tag**, **onde usar** e **descrição**)
- ✅ Botões:
  - **Abrir tudo**
  - **Fechar tudo**
  - **Modo “abrir só uma”**
- ✅ Atalhos:
  - **Ctrl/⌘ + K** → foca na busca
  - **Esc** → limpa a busca

---

## Como usar

Acesse a versão hospedada do projeto no link abaixo:

👉 **[PHPDoc Tags Cheat Sheet – Página hospedada](https://phpdoc.pages.dev/)**

---

## Tags incluídas (Tag → Onde usar → Descrição)

Abaixo está a lista completa das tags presentes no projeto, no **mesmo formato do HTML**:  
**Tag** — **Onde usar** — **Descrição**

### Básicas / mais usadas no dia a dia

- **@param** — Funções / métodos — Define o tipo e o significado de um parâmetro. IDEs e analisadores usam isso para autocomplete e validações estáticas.
- **@return** — Funções / métodos — Define o tipo do valor retornado. Muito útil quando o tipo nativo não expressa detalhes (ex.: array tipado).
- **@var** — Variáveis / propriedades — Declara o tipo de uma variável/propriedade quando o PHP não consegue inferir. Ajuda IDEs e analisadores.
- **@throws** — Funções / métodos — Indica quais exceções podem ser lançadas. Ajuda a entender o contrato e como tratar erros.

### “Mágicas” (comuns com ORMs / métodos dinâmicos)

- **@property** — Classes — Declara propriedades mágicas (via `__get/__set` ou ORMs) para IDE/analisador entenderem.
- **@property-read** — Classes — Propriedade mágica somente leitura (não deve ser setada diretamente).
- **@property-write** — Classes — Propriedade mágica somente escrita (casos específicos, ex.: password via setter mágico).
- **@method** — Classes — Declara métodos mágicos (via `__call/__callStatic`) para IDE/analisador reconhecer chamadas dinâmicas.

### Organização / documentação / manutenção

- **@deprecated** — Qualquer (função/classe/método/propriedade) — Marca como obsoleto. IDEs costumam alertar para evitar uso e migrar para alternativa.
- **@see** — Qualquer — Referência relacionada (classe, método, doc). Ajuda a navegar no projeto.
- **@link** — Qualquer — Link externo relacionado (documentação, issue, especificação).
- **@example** — Qualquer — Aponta um exemplo de uso (arquivo/snippet/caminho). Útil em libs e APIs internas.
- **@author** — Arquivo / classe — Declara autoria (muito usado em bibliotecas/geradores de docs).
- **@version** — Arquivo / classe — Indica versão do componente (útil em documentação e releases).
- **@since** — Qualquer — Marca desde qual versão (do projeto ou do PHP) aquilo existe.
- **@package** — Arquivo — Agrupamento lógico para documentação (mais comum em geradores de docs).
- **@subpackage** — Arquivo — Subgrupo dentro do package (uso mais raro hoje, mas aparece em projetos antigos).
- **@inheritdoc** — Métodos / classes — Indica que a documentação deve ser herdada do elemento pai (evita duplicação).

### Avançadas (tipagem estática / generics: PHPStan / Psalm)

- **@template** — Classes / interfaces / funções (generics) — Declara um tipo genérico (suportado por PHPStan/Psalm). Ajuda a manter tipagem forte em coleções/helpers.
- **@template-covariant** — Classes / interfaces (generics) — Declara um template covariante (mais comum em Psalm). Ajuda a modelar coleções somente-produtoras (read-only).
- **@extends** — Classes (generics) — Especifica o tipo ao estender uma classe genérica.
- **@implements** — Classes (generics) — Especifica o tipo ao implementar uma interface genérica.
- **@param-out** — Funções / métodos (analisadores estáticos) — Indica que um parâmetro será preenchido como saída para análise estática.
- **@phpstan-return** — Funções / métodos (PHPStan) — Define um tipo de retorno mais específico para o PHPStan.
- **@psalm-return** — Funções / métodos (Psalm) — Define um tipo de retorno mais específico para o Psalm.
