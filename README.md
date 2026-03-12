# Spinel for Zed

This repository is a theme-only port of Shopify's `Spinel` theme for the Zed editor.

## Included themes

- `Spinel Dark`
- `Spinel Light`

These themes are defined in:

- `themes/spinel.json`

## Recommended setup

For the best Ruby highlighting experience in Zed, use:

1. the official Ruby extension
2. `ruby-lsp`
3. semantic tokens enabled for Ruby
4. the Spinel theme from this repository
5. custom semantic token rules

For example:

```jsonc
{
  "theme": {
    "mode": "system",
    "light": "Spinel Light",
    "dark": "Spinel Dark"
  },
  "languages": {
    "Ruby": {
      "semantic_tokens": "combined",
      "language_servers": ["ruby-lsp", "!solargraph", "!rubocop", "..."]
    }
  },
  "global_lsp_settings": {
    "semantic_token_rules": [
      // ---------------------------------------------------------------------
      // This prevents parameters from being coerced into variables.
      {
        "token_type": "parameter",
        "style": ["parameter", "variable.parameter", "variable"]
      },
      // ---------------------------------------------------------------------

      // ---------------------------------------------------------------------
      // This makes builtins like `self` look distinct from variables.
      {
        "token_type": "variable",
        "token_modifiers": ["default_library"],
        "style": ["constant.builtin", "variable.special", "variable.builtin"]
      }
      // ---------------------------------------------------------------------
    ]
  }
}
```

## Credits

This theme is based on Shopify's Spinel theme from `vscode-shopify-ruby`.

Theme source:
https://github.com/Shopify/vscode-shopify-ruby/tree/main/themes
