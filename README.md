# Resume

The source of Bihan Qian's resume: `Bihan_Qian_Resume-Full.tex`, one page.

## Build

Tectonic 0.17.0, with a fixed date so the PDF is the same on every build:

```bash
cp Bihan_Qian_Resume-Full.tex Bihan_Qian_Resume.tex
SOURCE_DATE_EPOCH=0 tectonic -X compile Bihan_Qian_Resume.tex
```

The PDF is named `Bihan_Qian_Resume.pdf`; it is not committed.

## Layout the tailoring tool relies on

The personal MCP server (`tools/resume.py`) reads the newest commit of `main` and tailors this file to a job: it
rewrites the summary and reorders the bullets within each role, keeping every other word and the bold as written here. It needs:

- a `\heading{SUMMARY}` section whose text ends in `\par`;
- a `\name{...}` title over each `itemize` of `\item` bullets;
- skills lines written `\name{Label:} item, item, ...\par`;
- bold in the bullets or skills written as `\textbf{...}` around plain words (it is the same for every job);
- the body's 13bp line height, which is `LINE_PT` in `tools/resume.py` (change both together).

The repo is public because the server reads it without a token.
