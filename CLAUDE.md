# vj-ai-kit

Plugin do Claude (skills de animação, design de UI e referências de design systems). Conteúdo em `skills/` e `designs/`; manifestos em `.claude-plugin/`.

## Estrutura

- `skills/<nome>/SKILL.md`: uma skill por pasta, com frontmatter `name` e `description`. Módulos extras ficam ao lado do `SKILL.md`.
- `designs/<marca>/DESIGN.md`: referências de design systems, consultadas pela skill `design-references`.
- `skills/section-layouts/prompts/`: wireframes SVG usados pela skill `section-layouts`.
- Toda skill nova entra na tabela de skills do `README.md`. Se veio de terceiros, entra também em "Créditos".
- Skills são escritas em inglês; README e docs do repo em português.

## Versionamento e release (automático)

Decisões:
- **Conventional Commits** são obrigatórios nas mensagens de commit que entram na `main`. O tipo define o bump da versão.
- **release-please** cuida da versão, do `CHANGELOG.md`, da tag e da Release. Ninguém edita versão, cria tag ou publica release na mão.
- A versão vive em `.claude-plugin/plugin.json` (`version`) e `.claude-plugin/marketplace.json` (`plugins[0].version`). O release-please atualiza os dois juntos (`extra-files` em `release-please-config.json`) e registra a versão atual em `.release-please-manifest.json`. **Não edite esses três campos manualmente.**
- O `vj-ai-kit.plugin` é empacotado e anexado à Release pelo job `package` de `.github/workflows/release.yml`. Ele roda só quando uma Release é criada.

Fluxo:
1. Commits vão para a `main` (direto ou via PR) com mensagens convencionais.
2. O release-please abre/atualiza um PR "chore(main): release X.Y.Z" com a versão nova e o changelog.
3. Mergear esse PR cria a tag `vX.Y.Z`, a Release e o `vj-ai-kit.plugin`.

Tipos de commit:

| Tipo | Efeito | Exemplo |
|---|---|---|
| `feat:` | sobe a minor (1.0.0 → 1.1.0) | `feat: add section-layouts skill` |
| `fix:` | sobe a patch (1.1.0 → 1.1.1) | `fix: correct easing curve in animate` |
| `feat!:` ou rodapé `BREAKING CHANGE:` | sobe a major | `feat!: rename skill animate to motion` |
| `docs:`, `chore:`, `refactor:`, `style:`, `test:`, `ci:` | não geram release | `docs: update README table` |

Regras:
- Use escopo quando ajudar: `feat(ui-fundamentals): ...`.
- Mudança que quebra o nome de uma skill (renomear, remover) é breaking: usuários invocam como `/vj-ai-kit:<skill>`.
- Commits fora do padrão não quebram nada, mas são ignorados no changelog e não geram release.
- O repo precisa ter ligado em Settings → Actions → General: "Allow GitHub Actions to create and approve pull requests".

## Conteúdo de terceiros

- Skills de animação/UI: [emilkowalski/skills](https://github.com/emilkowalski/skills) (MIT).
- `ui-fundamentals` e `section-layouts`: adaptadas de [bergside/typeui](https://github.com/bergside/typeui) (MIT, © Bergside LLC). Decidimos não trazer o CLI (`src/`), o MCP nem os plugins de outras ferramentas.
- `designs/`: [designmd.co](https://www.designmd.co/).
- Ao adaptar conteúdo de terceiros, manter crédito no frontmatter ou no rodapé da skill e no README, e remover referências a arquivos que não vieram junto.
