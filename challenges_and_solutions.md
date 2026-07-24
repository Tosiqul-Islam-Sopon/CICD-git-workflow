## Challenges Faced & Solutions

### 1. YAML Syntax & GitHub Workflows Syntax
* **Challenge:** Being unfamiliar with YAML formatting and GitHub Actions syntax, I frequently ran into indentations and configuration syntax errors.
* **Solution:** Overcame this by repeatedly practicing workflow creation, studying action structures, and debugging syntax errors iteratively.

### 2. Deployment & Environment Issues (Self-Hosted Runner)
* **Challenge:** During initial deployments on the self-hosted runner, the job failed sequentially with environment errors—first returning `npm: command not found`, then `pm2: command not found`.
* **Solution:** Resolved the issues systematically using a step-by-step approach—first linking Node.js/npm to the runner's PATH, then configuring global access for PM2.

### 3. Artifact Upload Path Mismatch
* **Challenge:** The `upload-artifact` step failed because I provided a directory name instead of the exact target file path, leading to `No files were found` errors.
* **Solution:** Fixed the path parameter to point directly to the generated file (`test_result.txt`) instead of an uncreated directory.

### 4. Artifact Download & Extraction Path Logic
* **Challenge:** Encountered `Is a directory` and missing file errors during the download step due to misunderstanding how `download-artifact` handles destination paths vs. original filenames on the host runner.
* **Solution:** Configured a dedicated target directory (`test_result_dir`) for extraction and updated downstream step paths accordingly (e.g., `cat test_result_dir/test_result.txt`).