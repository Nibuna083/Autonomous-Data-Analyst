name=roles/Nibuna083.md
# Role: Query-to-Pandas & Report Generation Pipeline
Author: Nibuna083 (@Nibuna083)
Date: 2026-08-27

## Summary
I am responsible for converting analytical queries and data requirements into efficient pandas-based data transformation code and for building and maintaining the report-generation pipeline that produces reproducible, production-ready reports (HTML/PDF/XLSX) from cleaned DataFrames.

## Primary Responsibilities
- Translate business/analytic queries into clear, well-tested pandas transformations and pipelines.
- Design and implement memory- and performance-aware pandas code (vectorized operations, categorical usage, chunked processing where appropriate).
- Build and maintain the report generation pipeline that:
  - Accepts standardized DataFrame outputs,
  - Renders templates (Markdown/Jinja2/HTML),
  - Exports to HTML, PDF, and Excel formats,
  - Supports parameterization (date ranges, filters, aggregations).
- Automate pipeline execution and scheduling (local scripts, CI, or GitHub Actions).
- Create reproducible example notebooks and scripts showing the query -> pandas -> report flow.
- Write unit and integration tests for transformation functions.
- Document data contracts, expected input schema, and assumptions for downstream consumers.

## Key Contributions / Deliverables
- A library of transformation functions that map specific queries to pandas operations (filter, groupby, agg, pivot, merge, etc.).
- A report renderer that:
  - Accepts DataFrames or file inputs,
  - Applies report templates and styling,
  - Produces publication-ready outputs (HTML/PDF/XLSX).
- Examples and runnable scripts/notebooks demonstrating:
  - How to run a full data-to-report pipeline end-to-end,
  - How to add new query-to-pipeline mappings and new report templates.
- CI checks and tests ensuring transformations preserve schema and expected aggregates.
- Performance notes and recommended limits for in-memory processing; guidance for when to switch to chunking or Dask.

## How to use / run (examples)
- Run a single transformation and render a report:
  - python -m reports.generate --input data/input.csv --query my_query_key --out reports/my_report.html
- Run the pipeline in CI or local:
  - ./scripts/run_report_pipeline.sh --config configs/report_config.yml
- Run tests:
  - pytest tests/transformations tests/reports

(Adapt these commands to the repository's actual module/script names and CLI tools.)

## Testing & Validation
- Unit tests for each transformation function that:
  - Validate schema and dtypes,
  - Check sample inputs against expected aggregated outputs.
- Integration tests for the report pipeline that:
  - Ensure templates render without errors,
  - Confirm outputs are generated and include expected key values.
- Add small, deterministic fixtures to tests/fixtures for repeatable coverage.

## Code style & review
- Follow the repository's existing style (PEP8/black/isort if present).
- Include docstrings with examples for transformation functions.
- Provide a short usage example in README or a dedicated docs/section for adding new queries and templates.
- Suggested PR title/commit message: "Add role file for Nibuna083: query-to-pandas and report generation pipeline"

## Contact / Questions
- GitHub: @Nibuna083
- If you need more detailed run commands, mappings of queries to function names, or a sample template, I can add a runnable example or a small demo notebook.
