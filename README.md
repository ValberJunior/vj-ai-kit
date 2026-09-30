# vj-ai-kit

Um kit de skills para Claude que ajuda designers e engenheiros a construir interfaces melhores: animações, princípios de design, UI nativa em mobile, Swift moderno, e uma coleção de design systems de grandes marcas para usar como referência.

Empacotado como **plugin do Claude**, para instalar no Claude Code, Claude Desktop e Cowork.

## Por que usar?

Agentes não têm bom gosto por padrão. Escolhem `ease-in` para uma animação de entrada quando deveria ser `ease-out`, usam borda sólida no lugar de uma sombra semitransparente, animam propriedades que travam o frame. Esses detalhes pequenos se acumulam e separam uma interface ótima de uma interface apenas ok.

Estas skills listam esses erros e explicam como corrigi-los.

## Instalação

### Claude Code

Adicione o repositório como marketplace e instale o plugin:

```
/plugin marketplace add ValberJunior/vj-ai-kit
/plugin install vj-ai-kit@vj-ai-kit
```

Depois, rode `/reload-plugins` (ou reinicie o Claude Code). Para conferir, use `/plugin` e veja `vj-ai-kit` na aba **Installed**. As skills ficam disponíveis como `/vj-ai-kit:animate`, `/vj-ai-kit:review-animations` etc., e o Claude também as usa automaticamente quando a tarefa combina.

Para atualizar depois de uma nova versão:

```
/plugin marketplace update vj-ai-kit
```

Para testar localmente, sem instalar, a partir de uma cópia do repositório:

```bash
claude --plugin-dir ./vj-ai-kit
```

### Claude Desktop e Cowork

1. Baixe o `vj-ai-kit.plugin` na página de [Releases](https://github.com/ValberJunior/vj-ai-kit/releases/latest).
2. No app, abra **Plugins** (ou **Customize → Plugins**) e escolha **Upload plugin** / **Add plugin from file**.
3. Selecione `vj-ai-kit.plugin`. As skills passam a ficar disponíveis nas conversas e no Cowork.

### Só as skills, via CLI

```bash
npx skills@latest add ValberJunior/vj-ai-kit
```

## Publicar uma nova versão

1. Atualize `version` em `.claude-plugin/plugin.json` e em `.claude-plugin/marketplace.json`.
2. Faça commit e crie a tag com o mesmo número:

```bash
git tag v1.0.1
git push origin v1.0.1
```

A GitHub Action [release.yml](./.github/workflows/release.yml) empacota o plugin e anexa o `vj-ai-kit.plugin` na Release. Ela falha se a tag não bater com a versão do `plugin.json`.

Para gerar o pacote manualmente:

```bash
tar -a -cf vj-ai-kit.plugin .claude-plugin skills designs README.md LICENSE performance-cheatsheet.md
```

## Skills

| Skill | O que faz |
| --- | --- |
| [emil-design-eng](./skills/emil-design-eng/SKILL.md) | Skill principal: animação principalmente, mais conselhos de design. |
| [animate](./skills/animate/SKILL.md) | Constrói uma animação do zero, escolhendo curva, duração e propriedades corretas. |
| [animate-expo](./skills/animate-expo/SKILL.md) | O mesmo rigor para React Native e Expo: gestos, sheets, haptics, transições de tela e manter o movimento fora da thread JS. |
| [review-animations](./skills/review-animations/SKILL.md) | Revisa suas animações de forma estrita, com base em regras. |
| [improve-animations](./skills/improve-animations/SKILL.md) | Audita todas as animações do código e gera planos priorizados que qualquer agente executa. |
| [find-animation-opportunities](./skills/find-animation-opportunities/SKILL.md) | Encontra onde o movimento realmente ajuda, e diz o que não animar. |
| [animation-vocabulary](./skills/animation-vocabulary/SKILL.md) | Vocabulário certo para pedir exatamente a animação que você quer. |
| [apple-design](./skills/apple-design/SKILL.md) | Princípios de interface e movimento fluido da Apple (talks da WWDC), traduzidos para a web. |
| [write-swift](./skills/write-swift/SKILL.md) | Swift moderno: value types, concorrência do Swift 6, generics, performance e Swift Testing. |
| [pick-ui-library](./skills/pick-ui-library/SKILL.md) | Escolhe a biblioteca certa para a tarefa em vez de criar do zero ou instalar pacote abandonado. |
| [prototype](./skills/prototype/SKILL.md) | Gera várias versões de um componente de UI e permite alternar entre elas. |
| [mobile-native](./skills/mobile-native/SKILL.md) | Faz o web app parecer nativo no celular: hover preso, bug do 100vh, zoom em inputs, safe areas etc. |
| [ask-sonner](./skills/ask-sonner/SKILL.md) | Guia para a biblioteca de toasts [Sonner](https://sonner.emilkowal.ski). |
| [design-references](./skills/design-references/SKILL.md) | Consulta os design systems da pasta `designs/` como ponto de partida visual. |

Também incluído: [performance-cheatsheet.md](./performance-cheatsheet.md), uma tabela rápida de problemas comuns de performance em animação e suas soluções.

## Designs

A pasta [designs/](./designs) reúne interpretações inspiradas na linguagem visual de várias marcas: tokens de cor, tipografia, espaçamento, raios, elevação e padrões de componentes. Use como referência para pedir "no estilo de X" ou como ponto de partida para um tema.

| | | | |
| --- | --- | --- | --- |
| [Adobe](./designs/adobe/DESIGN.md) | [Airbnb](./designs/airbnb/DESIGN.md) | [Anthropic](./designs/anthropic/DESIGN.md) | [Apple](./designs/apple/DESIGN.md) |
| [Asana](./designs/asana/DESIGN.md) | [Atlassian](./designs/atlassian/DESIGN.md) | [BMW](./designs/bmw/DESIGN.md) | [Cloudflare](./designs/cloudflare/DESIGN.md) |
| [Cursor](./designs/cursor/DESIGN.md) | [Duolingo](./designs/duolingo/DESIGN.md) | [ElevenLabs](./designs/elevenlabs/DESIGN.md) | [Google](./designs/google/DESIGN.md) |
| [Linear](./designs/linear/DESIGN.md) | [Microsoft](./designs/microsoft/DESIGN.md) | [Netflix](./designs/netflix/DESIGN.md) | [Notion](./designs/notion/DESIGN.md) |
| [OpenAI](./designs/openai/DESIGN.md) | [Perplexity](./designs/perplexity/DESIGN.md) | [Ramp](./designs/ramp/DESIGN.md) | [Revolut](./designs/revolut/DESIGN.md) |
| [Spotify](./designs/spotify/DESIGN.md) | [Stripe](./designs/stripe/DESIGN.md) | [Supabase](./designs/supabase/DESIGN.md) | [Vercel](./designs/vercel/DESIGN.md) |

> Os arquivos são interpretações inspiradas, não assets oficiais. Marcas e logos pertencem aos seus respectivos donos.

## Créditos

As skills de animação e design de interface (`emil-design-eng`, `animate`, `animate-expo`, `review-animations`, `improve-animations`, `find-animation-opportunities`, `animation-vocabulary`, `apple-design`, `write-swift`, `pick-ui-library`, `prototype`, `mobile-native`, `ask-sonner`) vêm do repositório [emilkowalski/skills](https://github.com/emilkowalski/skills), de Emil Kowalski, licenciado sob MIT. Veja o [aiforui.dev](https://aiforui.dev/skills) para mais.

Os arquivos da pasta `designs/` foram obtidos em [designmd.co](https://www.designmd.co/). Marcas e nomes pertencem aos seus respectivos donos, e esses arquivos não são afiliados a nenhuma dessas empresas.

## Licença

A licença MIT deste repositório cobre o conteúdo original. A pasta `designs/` segue os termos do [designmd.co](https://www.designmd.co/).

[MIT](./LICENSE)
