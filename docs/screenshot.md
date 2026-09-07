# Executive for Typora

A port of the **Executive** VS Code theme to Typora, set in *Monaspace*. Deep jade greens, rich brown accents, and warm parchment text. Body copy is Monaspace Xenon with texture healing, `inline code` is Monaspace Neon, and [links](https://github.com/rgehrsitz/executive-typora-theme) take the theme's blue. Press <kbd>Ctrl</kbd>+<kbd>/</kbd> for source mode.

> Deep jade greens, rich brown accents, and a touch of refined taste — with **bold** and *italic* inside.

## Palette

| Role       | Colour    | VS Code key          |
|------------|-----------|----------------------|
| Background | `#181e21` | `editor.background`  |
| Text       | `#fdc78e` | `editor.foreground`  |
| Headings   | `#ff7353` | `markup.heading`     |
| Accent     | `#1c6f73` | `badge.background`   |

## Code

```typescript
// Monaspace Neon with ligatures: != === -> => <= >= :: |> </ />
import { readFile } from "node:fs/promises";

export async function loadTheme(path: string): Promise<Theme> {
  const raw = await readFile(path, "utf8");
  const parsed = JSON.parse(raw) as Partial<Theme>;
  if (parsed.name === undefined || parsed.weights?.length !== 3) {
    throw new Error(`invalid theme: ${path}`);
  }
  return { dark: true, ...parsed } as Theme;
}
```

> [!TIP]
> Every colour is a `--exec-*` variable annotated with the VS Code key it came from.

- [x] Port the palette
- [x] Bundle the Monaspace variable fonts
- [ ] Add a light variant
