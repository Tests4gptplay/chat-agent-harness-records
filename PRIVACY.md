# Privacy preparation

Windows profile names in archived diagnostics use the placeholder `USER`.
The complete task records, timestamps, results, and historical commit sequence are preserved.
Archive commit references in `INDEX.json` follow the sanitized history.

`source_blob_sha` and source-repository commit references identify the original source bytes; archived text containing the profile placeholder has been privacy-sanitized.
