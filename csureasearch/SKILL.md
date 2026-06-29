---
name: csureasearch
description: "Create or revise Chinese course-review research papers and Word documents with strict university-style requirements: title/cover metadata, template heading styles, figure/table captions, abstract and keywords, deep analytical body text, PDF/literature evidence management, figures from papers, GB/T 7714-2025 references, superscript bracket cross-references, citation order audits, rendered layout QA, and format preservation. Use when the user asks for CSUreasearch, Chinese term-paper review writing, long Word-format literature reviews, reference/citation cleanup, figure placement planning, or PDF-based manuscript drafting."
---

# CSUreasearch

Use this skill for Chinese course-review papers that must look like a finished Word assignment, not a loose report. Prioritize format correctness, citation traceability, and analytical depth.

## Default Assumptions

- Write in Chinese unless the user asks otherwise.
- Treat the document as a course assignment, not a journal submission.
- Follow explicit page-count requirements only when the user, course brief, or template specifies them.
- Use the user-provided Word template or prior example document. If the user says "不要更改格式", preserve all existing styles, spacing, headers, numbering, captions, and user edits except the requested local fixes.
- Use placeholders for unknown student name, student ID, course name, teacher, date, and title only when the user has not provided them.

## Document Structure

Include, in order:

1. Cover/title page following the provided template.
2. Chinese abstract and keywords.
3. Table of contents, updated after final edits.
4. Main body organized as a problem-driven technical review.
5. Figures/tables with captions and source notes.
6. References in citation order.

For the body, avoid a simple literature summary. Each major chapter should follow this pattern when possible:

`background problem -> technical progress -> representative literature comparison -> engineering applicability -> limitations and judgment`.

Make the central argument explicit. Good review writing should compare routes, evaluate evidence strength, expose boundary conditions, and state which claims are mature, uncertain, or only conceptual.

## Literature Workflow

Build an evidence base before drafting when PDFs or reference exports are available.

- Inventory PDFs and rename consistently as `Rxxx_year_short-title.pdf` when the user requests PDF cleanup.
- Create or update an evidence matrix with: reference number, language, year, title, authors, source, DOI/link, PDF status, technical object, scenario, contribution, limitations, usable section, core/non-core role, quantitative findings, figure/table candidates.
- Balance English literature with CNKI/Chinese literature when the user asks for Chinese references. Do not overfit to English papers if the assignment expects Chinese scholarship.
- If full PDFs are unavailable, use abstracts and metadata for screening, then tell the user which PDFs are needed for deeper reading.
- Do not fabricate papers, DOIs, page ranges, quantitative results, or figure sources.

## Citation Rules

Use GB/T 7714-2025 numeric sequential style unless the user specifies another style.

- Reference list order must follow first appearance in the main text (正文).
- In-text citations must be bracketed superscript cross-references, visually like `^[1]` or `^[2-4]` in Word display, not plain inline text.
- Set citation numbers to 小四 size, superscript, with bracket style matching the user's example.
- Prefer real Word bookmarks and `REF` fields for cross-references when editing DOCX.
- Each sentence or citation cluster may cite at most 5 actual references. Split claims into separate sentences instead of attaching dozens of references to one sentence.
- Delete uncited references unless the user explicitly wants a bibliography pool.
- Do not include access dates for ordinary journal, dissertation, conference, book, or report references. Avoid "引用日期" or "[2026-..-..]" unless the user specifically requires web access dates.
- For web pages, official notices, policies, standards, and accident/safety reports, prefer authoritative sources and keep the GB/T entry concise and traceable.
- After inserting figures, re-audit citation order because figure captions can change first-citation order.

## Figure And Table Rules

Use figures only when they support analysis.

- Prefer 8-12 high-value figures/tables for a standard long review unless the user asks for more candidates.
- Good figure types: mechanism schematics, model architecture, experimental setup, validation comparison, task flow, technology map, maturity matrix, quantitative evidence table.
- For original paper figures, caption with "引自文献[序号]".
- For redrawn or synthesized figures, caption with "根据文献[序号]整理/改绘".
- Every figure/table must have a number, caption, source note, and an in-text reference.
- Apply the template caption styles: figures use `6_图序图名（之间空一格）`; tables use `8_表序表名`.
- Keep figure order sequential. If a user adds figures and disrupts citations, fix only citation/reference order unless asked to rewrite.
- Avoid low-resolution screenshots when a clean redraw or higher-quality PDF capture is possible.

## Template Heading And Caption Styles

When using the `杨传梁_高超声速飞行器降热设计.docx` template or a document derived from it, preserve and reuse these styles instead of recreating direct formatting.

- Cover course title: centered, 黑体, 40 pt (`w:sz=80`).
- Cover metadata labels, student name/ID, topic, course name, and date: centered, 黑体, 16 pt (`w:sz=32`).
- Level 1 heading style `1_一级标题`: automatic numbering `第%1章`; centered; page break before; outline level 0; 黑体 for Chinese, Times New Roman for Latin; 16 pt (`w:sz=32`); bold; exact 20 pt line spacing (`line=400`); 18 pt before (`before=360`) and 12 pt after (`after=240`).
- Level 2 heading style `2_二级标题`: automatic numbering `%1.%2`; outline level 1; 宋体 for Chinese, Times New Roman for Latin; 14 pt (`w:sz=28`); exact 20 pt line spacing; 10 pt before and 8 pt after.
- Level 3 heading style `3_三级标题`: automatic numbering `%1.%2.%3`; outline level 2; 宋体 for Chinese, Times New Roman for Latin; 小四/12 pt (`w:sz=24`); exact 20 pt line spacing; 10 pt before and 8 pt after.
- Level 4 heading style `4_四级标题`: automatic numbering `%1.%2.%3.%4`; outline level 3; use the template style if present; do not fake numbering manually.
- Body style `0_正文`: 宋体 for Chinese, Times New Roman for Latin; 小四/12 pt (`w:sz=24`); first-line indent 2 Chinese characters; exact 20 pt line spacing.
- Figure caption style `6_图序图名（之间空一格）`: centered; caption placed below the figure; format `图N 图名` with one space between number and title; 楷体 for Chinese, Times New Roman for Latin; 五号/10.5 pt (`w:sz=21`, `w:szCs=22`); exact 20 pt line spacing; 5 pt after.
- Table caption style `8_表序表名`: centered; caption placed above the table; format `表N 表名` with one space between number and title; 楷体 for Chinese, Times New Roman for Latin; 五号/10.5 pt (`w:sz=21`, `w:szCs=22`); exact 20 pt line spacing; 5 pt before.
- Table body style `7_表格`: centered; no first-line indent; 五号/10.5 pt (`w:sz=21`); use template table borders, widths, and cell padding where available.
- Use Word automatic heading numbering and TOC generation. Do not type chapter numbers, figure numbers, table numbers, or TOC entries by hand unless the template explicitly requires static text.

## Word Formatting And QA

Always treat Word layout as a deliverable.

- Use the provided DOCX template as the style authority.
- Preserve user-applied formatting when revising an existing document.
- Keep headings, automatic numbering, TOC, captions, and references visually consistent with the template styles.
- Render the final DOCX to PDF/PNG for visual checking when tools are available.
- Verify page count, TOC population, no blank/near-blank structural pages except intentional cover/section pages, readable tables, clear figures, correct caption placement, and no overlapping text.
- Audit citation fields: all visible citations should be superscript, 小四, bracketed, sequential, and traceable to a reference entry.
- Check that every reference is cited and every cited number has a bibliography entry.

## Writing Standards

- Write as a review with depth, analysis, and evaluation.
- Use quantitative results only with conditions and caveats: Mach number, Reynolds number, altitude, gas model, wall condition, experimental/numerical method, scale effect, and uncertainty where available.
- Do not rank technologies only by reported drag-reduction percentage unless the conditions are comparable.
- Discuss engineering tradeoffs: drag, heat flux, stability, propulsion integration, structural mass, energy/resource cost, reliability, controllability, manufacturability, and verification maturity.
- Use comparison tables for route-level judgments, but avoid turning the whole paper into tables.
- Use official reports or authoritative primary sources for accident, safety, policy, and standards claims.

## Typical Deliverables

Depending on the request, produce some or all of:

- `pdf_inventory.csv`
- `evidence_matrix.csv` or `.xlsx`
- `reference_registry_gbt2025.xlsx` or `.csv`
- `figure_inventory.csv`
- final `主题.docx`
- rendered `主题_排版检查.pdf`
- optional `figures/` folder with source captures, redraws, SVG/PNG exports, and contact sheets.

## Final Checks Before Delivery

Before saying the task is complete, verify:

- If a page-count requirement is explicitly given, the rendered page count meets it.
- The title, cover metadata, abstract, keywords, TOC, main text (正文), figures/tables, and references are present.
- Template heading styles, figure captions, table captions, table body style, and automatic numbering are preserved or correctly applied.
- References are GB/T 7714-2025 style and contain no unwanted access dates.
- Citation order is sequential after figure captions.
- No citation cluster exceeds 5 actual references.
- No uncited bibliography entries remain unless requested.
- The final answer links the main DOCX and only the requested supporting files.
