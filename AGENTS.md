# Working on poblocki.pl

This is the family’s own site, in Polish and English. The published pages speak as the family. They do not argue with the family story, and they do not read like a researcher’s notes.

The live site is <https://poblocki.family>. GitHub Pages builds the `master` branch. Open pull requests against `master`.

## Pages

- `pl/` is the original. `en/` is the translation. Keep them in step.
- A page in each language shares the same `ref` in the front matter. Header labels live in `_data/i18n.yml`.
- The family history is the landing page: `/pl/` and `/en/`. There is no separate home page. Old `/pl/family-history/` and `/en/family-history/` redirect there.
- Navigation is Historia rodu / Pobłocie / Herb, and the English equivalents. Do not add “Strona główna”.
- Dates on the site are ISO `YYYY-MM-DD`.

## Voice

Write the fact. Do not write “opis rodzinny wymienia”, “the family account says”, “this is not confirmed”, or “the stone repeats the dates”.

If something is unknown or does not make sense, leave it off the page and put it only in `_research/summary.md`. That folder is unpublished.

Do not invent the unnamed son or daughter of Zygmunt and Zofia Woyke, or Bogusław’s wife’s maiden name. The two Zofias stay distinct: Zofia née Woyke, and Bogusław’s wife Zofia. Living names may appear. Do not copy street addresses or phone numbers from the Münster letters into the repo.

Do not merge this Pobłocie (gmina Linia) with the Kołobrzeg Pobłocie, German Pobloth. Do not use that German-page photo.

These stay off the published pages, even if a source suggests them: Emilia’s birth year; Kulturkampf; Dr Juliusz as a court president who died in a camp; Stanisław murdered in 1939; Jadwiga in Gryf Pomorski; the proposed coat-of-arms colors; identifying the Stevens Point atlas with this Władysław. The Chełmno grave list stays the family’s transcription. Albert’s parish in Niedźwiedź is stated, not questioned.

## Layout

Custom CSS is in `_includes/head-custom.html`, after the Slate theme.

- The text column is 78% of the window.
- Language links sit at the top right: the Polish flag, then the United States flag.
- Every picture in the text is 60% of the column, centered, inside a `<figure>`. The coat of arms is the exception: it is smaller and sits to the left of its description.
- The family history shows `images/linia-sign.jpg` under chapter I. The Pobłocie page shows `images/poblocie-entrance.jpg`.
- The footer is one line: `poblocki.family`, who maintains it, and the GitHub link. Do not add “Published with GitHub Pages”.

## Local preview

Ruby is not installed. The real GitHub Pages build runs in Docker. Start Docker Desktop, then:

```powershell
docker run --rm --name poblocki-pages -p 4000:4000 -e JEKYLL_ENV=production -v "c:\Code\git\poblocki.pl:/srv/jekyll" jekyll/jekyll:pages jekyll serve --host 0.0.0.0 --destination /tmp/_site --force_polling --watch
```

Open <http://127.0.0.1:4000/pl/>. This image is the GitHub Pages Jekyll environment, so Liquid, the theme, and the redirects are the real ones. Do not treat the hand-built `preview*.html` files as the site. Do not commit them.

## Git

Commit and push only when asked. On PowerShell, pass the commit message with a here-string, not a bash heredoc. Do not commit `preview.html`, `preview-*.html`, `_preview.html`, or `_preview-theme.css`.
