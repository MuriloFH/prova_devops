# 📚 Workflow Git

Este projeto utiliza uma **variação do Git Flow** como modelo de versionamento e organização de branches.

---

## 📌 Modelo Adotado

- Baseado no **Git Flow**, com pequenas adaptações para simplificar o fluxo de desenvolvimento.
- Os branches seguem a seguinte hierarquia:

> `features` → `develop` → `main`

---

## 🌱 Estratégia de Branches

### `main`
- Contém sempre o código **estável** e **pronto para produção**.
- **Nunca** recebe commits diretamente.
- É atualizada **exclusivamente via merges da branch `develop`**.

### `develop`
- Branch de integração.
- Recebe merge de todas as features, correções, refatorações, etc.
- Após validação e testes, é integrada à `main`.

### `features/*`
- Criadas a partir de `develop` para implementar novas funcionalidades.
- Nomeadas com o prefixo `features/` seguido do nome descritivo da funcionalidade.
- Exemplo: `features/login-form`.

---

## 🔄 Regras de Atualização

- **Novas funcionalidades** (features), **correções** (fix), **refatorações** (refactor) e **ajustes de segurança** (sec) devem ser desenvolvidos em branches específicas e integrados à `develop`.
- Após validação e testes em `develop`, é feito o merge para `main`.

---

## Política de Revisão do Código

Para garantir a qualidade e a estabilidade do projeto, todas as alterações que forem integradas à branch `develop` devem passar por um processo de revisão de código rigoroso. Isso inclui merges diretos, pull requests (PRs) ou qualquer outro tipo de integração.

### Diretrizes principais:

- **Revisão Obrigatória:** Nenhuma alteração pode ser incorporada à branch `develop` sem aprovação prévia por pelo menos um revisor qualificado do time.
- **Pull Requests:** Toda alteração deve ser submetida via Pull Request para a branch `develop`, permitindo discussão, comentários e melhorias antes da integração.
- **Análise de Código:** Os revisores devem analisar cuidadosamente:
  - A clareza e qualidade do código.
  - A aderência ao padrão de commits e ao estilo do projeto.
  - A cobertura e qualidade dos testes automatizados.
  - Impactos na segurança e performance.
- **Correções Pós-Revisão:** Caso sejam apontadas mudanças necessárias, o autor do código deve realizar os ajustes antes que o merge seja aprovado.
- **Responsabilidade:** É responsabilidade de todos os membros do time participar ativamente das revisões para manter a qualidade coletiva do código.

---

> 💡 **Nota:** A branch `main` receberá atualizações apenas a partir da branch `develop` após validações adicionais, mantendo a estabilidade do código em produção.


---

## ✅ Convenção de Commits (Semântica)

Utilizamos **commits semânticos** para manter o histórico limpo e compreensível.

### Formato geral:

> `<tipo>(#ID): descrição do commit`

### Tipos permitidos

Abaixo estão os tipos de commits permitidos no fluxo de desenvolvimento deste projeto. Cada tipo representa uma intenção clara da mudança feita no código ou na base do projeto.

*Observação: Todos os commits devem ser totalmente em inglês.*

| Tipo        | Descrição                                                                                  | Exemplo                                      |
|-------------|---------------------------------------------------------------------------------------------|----------------------------------------------|
| `feat`      | Adição de nova funcionalidade ao projeto.                                                  | `feat(#23): add new payment method`          |
| `fix`       | Correção de bugs que afetam o comportamento do sistema.                                     | `fix(#45): fix navbar toggle issue`          |
| `docs`      | Atualizações ou criações de documentação técnica ou de usuário.                             | `docs(#50): update README with usage steps`  |
| `refactor`  | Refatorações no código que não alteram o comportamento externo da aplicação.               | `refactor(#12): simplify login logic`        |
| `style`     | Alterações de estilo que não afetam a lógica do código (ex: identação, aspas, ponto e vírgula). | `style(#67): format CSS classes`             |
| `test`      | Criação ou modificação de testes automatizados.                                             | `test(#31): add unit tests for comment form` |
| `chore`     | Tarefas que não modificam o código de produção ou testes (ex: configs, scripts, .gitignore). | `chore(#10): update .gitignore and env vars` |
| `sec`       | Mudanças relacionadas à segurança, como validações ou criptografia.                         | `sec(#34): add JWT validation middleware`    |
| `content`   | Criação ou atualização de conteúdo do blog.                                                 | `content(#75): add post about RESTful APIs`  |
| `seo`       | Melhorias para otimização em mecanismos de busca (Search Engine Optimization).              | `seo(#93): add meta tags to detailed posts`  |

> 💡 **Nota**: O `#ID` refere-se ao número da issue ou tarefa relacionada (ex: GitHub Issues, Jira, etc).

---

Cada commit deve começar com o tipo apropriado, seguido opcionalmente pelo número da issue entre parênteses, dois-pontos e a descrição clara da mudança.

**Formato sugerido:**

```
<tipo>(#ID): descrição clara da alteração
```

**Exemplo:**

```
feat(#101): implement post filtering by category
```

