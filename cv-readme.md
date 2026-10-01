# CV (RenderCV) — English & Spanish

Two versions, same content:

| File | Language | Locale |
| ---- | -------- | ------ |
| `cv_en.yaml` | English | `language: english` |
| `cv_es.yaml` | Spanish (full translation) | `language: spanish` (built-in, renders `present → presente`, `Jan → ene`, etc.) |

`neural.yaml` is a separate tailored variant, untouched.

## Render

Both files use the same `cv.name`, so both generate
`Javier_Emmanuel_Mercedes_CV.pdf` by default and would overwrite
each other in `rendercv_output/` (gitignored). Render with distinct
output paths:

```bash
# English
rendercv render cv_en.yaml --pdf-path Javier_Emmanuel_Mercedes_CV_EN.pdf

# Spanish
rendercv render cv_es.yaml --pdf-path Javier_Emmanuel_Mercedes_CV_ES.pdf
```

Or render everything to separate folders:

```bash
rendercv render cv_en.yaml -o rendercv_output/en
rendercv render cv_es.yaml -o rendercv_output/es
```

## Notes

- `cv_en.yaml` is the source of truth (ported from the old `cv.yaml`, plus `securiy` typo fix).
- Keep both files in sync when updating experience, projects, skills, etc. — translate accordingly.
- Validate with `rendercv render <file>` (strict validation; fails on bad dates/keys).
