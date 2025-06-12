# Installation & Setup
### 1. setup project with git
``` bash
git init <name of project>
```
### 2. setup virtual environment
[[$venv]]

### 3. Basic Installation
Inside your project directory with venv activated:
``` bash
pip install crawl4ai
```
This installs the core Crawl4AI library along with essential dependencies. No advanced features (like transformers or PyTorch) are included. 

### 4. Initial setup & Diagnostics
#### 4.1 Run the Setup command
After installing, call:
``` bash
crawl4ai-setup
```
Installs or updates required Playwright browsers (Chromium, Firefox, etc.) - Performs OS-level checks (e.g. missing libs on Linux) - Confirms your environment is ready to crawl.

#### 4.2 Diagnostics
Optionally, you can run diagnostics to confirm everything is functioning:
``` bash
crawl4ai-doctor
```
This command attempts to: - Check Python version compatibility - Verify Playwright installation - Inspect environment variables or library conflicts. 

If any issues arise, follow its suggestions (e.g., installing additional system packages) and re-run `crawl4ai-setup`.