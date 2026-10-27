# app-store-listing

> Una ficha de tienda que vende lo que la app hace y declara lo que la app recoge.

**Ficha de tienda de apps** · Skill para agentes de código de la comunidad [nvvdev](https://github.com/nvv-dev). Funciona en Claude Code como plugin o como skill suelta, y en cualquier agente compatible con el formato abierto [`SKILL.md`](https://agentskills.io).

*English summary at the end.*

## Qué hace

Prepara la ficha de Google Play y App Store: nombre, subtítulo o descripción corta, descripción larga, palabras clave por idioma, guion de capturas y notas de versión, con el conteo de caracteres contra el límite de cada campo. Compara la ficha y la app con la sección de seguridad de datos de Play y las etiquetas de privacidad de Apple y lista cada diferencia. Solo describe funciones que ya están en producción.

## Objetivo

Pasar la revisión de la tienda a la primera y que la ficha no prometa más de lo que la app hace o declara.

## Cuándo usarla

- Antes de enviar una app a revisión o de salir de una prueba cerrada
- Al agregar un idioma o un SDK que recoge datos

## Cuándo no

- Para enviar o publicar la ficha: la skill entrega textos, no toca las consolas
- Revisión legal a fondo de la política: usa legal-pages-check

## Ejemplo

```text
Prepara con app-store-listing la ficha de Widget Studio en español e inglés para Play Store.
```

## Cómo se activa

Esta skill **se activa sola**: Claude Code lee su descripción y la carga cuando la tarea coincide. También puedes pedirla por nombre ("usa la skill app-store-listing") o invocarla con `/app-store-listing:app-store-listing` (plugin) o `/app-store-listing` (copiada a `.claude/skills/`).

## Instalación

### Opción 1: Claude Code, como plugin (recomendada)

Dentro de Claude Code:

```text
/plugin marketplace add nvv-dev/claude-plugins
/plugin install app-store-listing@nvvdev
```

La primera línea agrega el catálogo de nvvdev una sola vez; la segunda instala esta skill. Si prefieres el paquete completo, instala `growth-workflow@nvvdev` en su lugar (incluye esta skill y las demás de [growth-workflow](https://github.com/nvv-dev/growth-workflow)); no instales los dos a la vez.

### Opción 2: Claude Code, copiando la skill

Para un solo proyecto (se comparte con tu equipo por git):

```bash
git clone --depth 1 https://github.com/nvv-dev/app-store-listing.git /tmp/app-store-listing
mkdir -p .claude/skills
cp -R /tmp/app-store-listing/skills/app-store-listing .claude/skills/
```

Para todos tus proyectos, cópiala en `~/.claude/skills/` en lugar de `.claude/skills/`.

### Opción 3: otros agentes

Copia la carpeta `skills/app-store-listing/` en la carpeta de skills de tu agente (cada agente documenta la suya). Con la CLI [skills](https://github.com/vercel-labs/skills) de Vercel Labs:

```bash
DISABLE_TELEMETRY=1 npx skills add nvv-dev/app-store-listing
```

### Verificar

Abre una sesión nueva y pregunta "¿qué skills tienes disponibles?"; `app-store-listing` debe aparecer. Con el plugin, `/plugin` la muestra como instalada.

### Actualizar o desinstalar

- Plugin: `/plugin marketplace update nvvdev` para actualizar; `/plugin uninstall app-store-listing@nvvdev` para quitarla.
- Copia manual: repite la copia para actualizar, o borra la carpeta `.claude/skills/app-store-listing`.

Antes de instalar cualquier skill, incluida esta, conviene leerla: es un solo archivo, [`skills/app-store-listing/SKILL.md`](skills/app-store-listing/SKILL.md). Ver [vetting-external-skills](https://github.com/nvv-dev/vetting-external-skills).

## Contenido

| Ruta | Qué es |
|---|---|
| `skills/app-store-listing/SKILL.md` | La skill: instrucciones en inglés para que los escáneres de seguridad las analicen completas; el agente responde en tu idioma |
| `.claude-plugin/plugin.json` | Manifiesto para instalarla como plugin |
| `.github/workflows/` | Validación de estructura y escaneo con SkillSpector en cada cambio |

## Contribuir

Este repo se **genera** desde [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow), donde vive la versión canónica. Abre issues y PRs allí. La mejor contribución es un caso real en la sección *Known failures* de la skill, con la regla que lo evita.

## Origen

Escrita desde cero por nvvdev. Inspirada en: [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) (aso).

## Licencia

MIT.

---

## English

**app-store-listing** — Writes Play Store and App Store listings (title, descriptions, screenshot script, keywords per language) consistent with the data safety section and privacy labels.

Install in Claude Code with `/plugin marketplace add nvv-dev/claude-plugins` and `/plugin install app-store-listing@nvvdev`, or copy `skills/app-store-listing/` into `.claude/skills/` (project) or `~/.claude/skills/` (personal). Other agents: copy the folder into their skills directory, or run `DISABLE_TELEMETRY=1 npx skills add nvv-dev/app-store-listing`. Loads automatically when the task matches its description. Canonical source: [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow). License: MIT.
