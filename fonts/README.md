# Fonts

The homepage is set in **Seriously Nostalgic Serif** by Nicky Laatz.

It is a licensed commercial typeface, so the font files are deliberately not
committed to this repository. Until they are present, the page falls back to
**Bodoni Moda** (loaded from Google Fonts), which shares the same high-contrast
eighties-magazine character.

## Dropping the real font in

Buy or locate your licensed copy, convert it to `.woff2` if you only have
`.otf`, and place the files in this folder using exactly these names:

```
fonts/SeriouslyNostalgic-Regular.woff2
fonts/SeriouslyNostalgic-Italic.woff2
```

`.otf` also works and is already listed as a secondary source in the
`@font-face` rules, so this is equally valid:

```
fonts/SeriouslyNostalgic-Regular.otf
fonts/SeriouslyNostalgic-Italic.otf
```

No code change is needed. The `@font-face` declarations at the top of
`index.html` pick the files up automatically, and every headline, the wordmark,
the creed and the mantra switch over on the next page load.

## Converting OTF to WOFF2

`.woff2` is roughly a third of the size and loads noticeably faster. Any
reputable font converter will do it, or locally:

```
pip install fonttools brotli
fonttools ttLib.woff2 compress SeriouslyNostalgic-Regular.otf
```

## Licensing note

Web embedding is a separate permission from desktop use in most font licences.
Check that the licence covers webfont use before publishing the files, since
anything in this folder is served publicly once the site is live.
