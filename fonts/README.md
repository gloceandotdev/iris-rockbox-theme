# InTofu

The fonts in each variant's `.rockbox/fonts/` are a single merged typeface called
**InTofu**:

- [Inter](https://rsms.me/inter/) 3.19 ("Hinted for Windows") supplies Latin,
  Greek, Cyrillic and symbols.
- [Noto Sans SC](https://fonts.google.com/noto/specimen/Noto+Sans+SC) supplies
  CJK ideographs, kana, bopomofo and fullwidth forms.
- [Noto Sans KR](https://fonts.google.com/noto/specimen/Noto+Sans+KR) supplies
  Hangul and Korean variants of shared CJK codepoints.

Inter wins on any codepoint it covers; the two Noto fonts fill the rest of the
Basic Multilingual Plane. The merged TTF is rasterized with Rockbox's
[`convttf`](https://www.rockbox.org/wiki/Tools) at each size into a single
bitmap font, which is why the theme needs no runtime font fallback (Rockbox
has none).

## Fonts

| File                     | Size   | Usage                                  |
|--------------------------|--------|----------------------------------------|
| `11-InTofu-SemiBold.fnt` | 11 px  | Topbar titles                          |
| `12-InTofu-Regular.fnt`  | 12 px  | Body text                              |
| `16-InTofu-Medium.fnt`   | 16 px  | Default UI font (themes cfg)           |
| `16-InTofu-Bold.fnt`     | 16 px  | Emphasis / now playing title           |
| `60-InTofu-SemiBold.fnt` | 60 px  | Sidebar clock (digits only, pure Inter)|

All variants ship byte-identical fonts, so installing several themes adds no
extra space on the player.

## Rebuilding

`tools/build-intofu.sh` rebuilds the fonts from scratch. It needs:

- a C compiler and FreeType 2 (`pkg-config freetype2`)
- Python 3 with `fonttools` (`pip install fonttools`)

It downloads Rockbox's `convttf`, Inter 3.19, Noto Sans SC and Noto Sans KR,
merges them per weight, and writes the `.fnt` files into `iris/.rockbox/fonts/`
plus a copy into each variant. Run it from the repo root:

```
tools/build-intofu.sh
```

## Notes

- Glyph widths in the `.fnt` are ink widths (what `convttf` produces), matching
  how the theme's original Inter fonts were built. CJK glyphs are therefore
  proportional rather than strictly fullwidth.
- The bundled `.fnt` files are derived from Inter and the Noto fonts; both are
  licensed under the SIL Open Font License 1.1. See
  `.rockbox/fonts/Inter-License.txt` and `.rockbox/fonts/Noto-License.txt`.
