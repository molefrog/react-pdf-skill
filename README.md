```
'########::'########::::'###:::::'######::'########:'########::'########::'########::::
 ##.... ##: ##.....::::'## ##:::'##... ##:... ##..:: ##.... ##: ##.... ##: ##.....:::::
 ##:::: ##: ##::::::::'##:. ##:: ##:::..::::: ##:::: ##:::: ##: ##:::: ##: ##::::::::::
 ########:: ######:::'##:::. ##: ##:::::::::: ##:::: ########:: ##:::: ##: ######::::::
 ##.. ##::: ##...:::: #########: ##:::::::::: ##:::: ##.....::: ##:::: ##: ##...:::::::
 ##::. ##:: ##::::::: ##.... ##: ##::: ##:::: ##:::: ##:::::::: ##:::: ##: ##::::::::::
 ##:::. ##: ########: ##:::: ##:. ######::::: ##:::: ##:::::::: ########:: ##::::::::::
..:::::..::........::..:::::..:::......::::::..:::::..:::::::::........:::..:::::::::::
:'######::'##:::'##:'####:'##:::::::'##:::::::
'##... ##: ##::'##::. ##:: ##::::::: ##:::::::
 ##:::..:: ##:'##:::: ##:: ##::::::: ##:::::::
. ######:: #####::::: ##:: ##::::::: ##:::::::
:..... ##: ##. ##:::: ##:: ##::::::: ##:::::::
'##::: ##: ##:. ##::: ##:: ##::::::: ##:::::::
. ######:: ##::. ##:'####: ########: ########:
:......:::..::::..::....::........::........::
```

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill for generating PDF documents
with [React-PDF](https://react-pdf.org/) (`@react-pdf/renderer`).

Install:

```
npx skills add molefrog/skills --skill pdf

# or as a claude code plugin
/plugin marketplace add molefrog/skills
/plugin install pdf@skills
```

## Why React-PDF over Python PDF libraries?

Libraries like ReportLab, WeasyPrint, or fpdf2 work, but React-PDF has real advantages for
AI-generated documents:

- **Flexbox & grid layout** — powered by Yoga (Facebook's layout engine). Centering, columns,
  wrapping grids — it just works. No absolute coordinate math.
- **SVG primitives** — `<Svg>`, `<Path>`, `<Circle>` are first-class components. Draw charts and
  icons inline without a separate graphics library.
- **Component composition** — build PDFs like React components. Reusable headers, tables, cards —
  all composable with props. Declarative, not imperative.
- **Google Fonts support** — register any TrueType font with `Font.register()`. The skill bundles a
  reference of ~65 popular Google Fonts with direct download URLs.
- **Knuth-Plass line breaking** — the same algorithm used by TeX. Produces professionally typeset
  paragraphs with proper hyphenation.
- **Smart page breaks** — `wrap`, `break`, `minPresenceAhead` control content flow across pages
  declaratively. Orphan/widow control built in.
- **Emoji support** — register Twemoji assets and use emoji directly in text. No custom rendering logic needed.

## License

MIT
