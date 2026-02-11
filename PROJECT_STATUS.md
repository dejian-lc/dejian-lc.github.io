# Project Status (al-folio)

## Overview
- Repo: `dejian-lc.github.io` (al-folio template)
- Local dev via Docker: `docker compose up` (http://localhost:8080)
- CV PDF generation: local RenderCV inside container using venv at `/srv/jekyll/.venv`

## Key Changes (Config / Content)
- `_config.yml`
  - `url: https://dejian-lc.github.io`, `baseurl:` empty
  - Scholar author set to `Liu, Chang`
  - Publication badges: `altmetric=false`, `dimensions=false`, `inspirehep=false`, `google_scholar=true`
  - `max_author_limit` empty (show all authors)
- `_data/socials.yml`
  - Keep only: CV PDF, email, GitHub, Google Scholar
  - `scholar_userid: ihHKAmYAAAAJ`
  - `cv_pdf: /assets/rendercv/rendercv_output/Chang_Liu_CV.pdf`
- `_pages/about.md`
  - Left/right profile as right
  - Photo info uses icons
  - Subtitle: `PhD Student, National University of Defense Technology`
  - Research interests: generative detection, multimodal models, AIGC, world models
  - Motto (EN italic)
  - Education snippet (PhD, Early-start, 2024.03–Present)
- `_news/announcement_1.md`
  - `[2025-06-26] HumanSAM is accepted by ICCV 2025!` with emoji
  - Removed `_news/announcement_2.md` and `_news/announcement_3.md`

## Publications
- `_bibliography/papers.bib` contains 3 papers and all are `selected = {true}`:
  1. ICCV 2025 HumanSAM (ICCV CCF A), co-first authors marked with `*`, annotation added
     - `google_scholar_id: u5HHmVD_uO8C`
     - `website: https://dejian-lc.github.io/humansam/`
     - `preview: humansam.jpg` (placed in `assets/img/publication_preview/`)
  2. ICIC 2025 TS-KFNet (ICIC CCF C)
  3. TCSVT 2025 Non-local Guided Neural Fields (TCSVT CCF B)

## CV (RenderCV)
- `_data/cv.yml` rebuilt with:
  - Education entries (BEng LZU 2018-09–2022, MEng NUDT 2022-09–2023-12, PhD NUDT 2024-03–Present)
  - Publications section added (3 papers)
- Local PDF generated at:
  - `assets/rendercv/rendercv_output/Chang_Liu_CV.pdf`

## Publications UI tweaks
- Preview thumbnails enlarged (`_layouts/bib.liquid`, `_sass/_publications.scss`)
- Website + Google Scholar badges are in the same container and aligned
- Website badge uses shields.io

## Local PDF Generation
1. Venv created in container: `/srv/jekyll/.venv`
2. Generate PDF:
   ```bash
   docker compose exec jekyll bash -lc "/srv/jekyll/.venv/bin/rendercv render _data/cv.yml --settings assets/rendercv/settings.yaml && rm assets/rendercv/rendercv_output/*.typ"
   ```

## Known Issues / Notes
- If Jekyll fails to refresh, run:
  ```bash
  docker compose restart
  ```
- Ensure `assets/img/publication_preview/humansam.jpg` exists

## TODO / Open Questions
- Confirm CV text/wording for Education and mottos
- Decide whether to include more sections (Experience, Awards, etc.) in CV
- Commit & push changes
