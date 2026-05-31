# LinkedIn AI Auto Job Applier 🤖

A tool to automate job search and Easy Apply on LinkedIn. It can search for jobs, fill application forms, upload resumes, and (optionally) use AI to help answer free-text questions.

This repository contains the bot code, configuration files, and helper scripts to run the automation locally. Use responsibly and follow LinkedIn's terms of service.

## Contents

- Introduction
- Install
- Configure
- Run
- Contributor guidelines
- Major updates
- Disclaimer & License
- Community and support

## Introduction

This project automates the Easy Apply experience on LinkedIn for configured searches and filters. It is intended to save time for repetitive applications; it is not guaranteed to work on all job pages and may require occasional manual intervention.

## Install

Requirements:

- Python 3.10 or newer
- Google Chrome (latest stable recommended)

Install dependencies (recommended inside a virtualenv):

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

If `requirements.txt` is not present, install core packages:

```bash
pip install undetected-chromedriver pyautogui setuptools flask flask-cors
```

Notes:

- On macOS you may need to install certificates: run the `Install Certificates.command` provided with your Python installer or set `SSL_CERT_FILE` using `certifi`.
- Keep Chrome updated. The bot will attempt to download a matching ChromeDriver when running in stealth mode.

## Configure

Before running the bot, edit the following files under the `config/` folder:

- `personals.py` — your name, contact, and address fields used in applications.
- `questions.py` — common answers and resume path.
- `search.py` — search terms, locations and job filters.
- `secrets.py` — (optional) LinkedIn username/password and AI provider settings. If credentials are not provided the tool will ask you to log in manually.
- `settings.py` — runtime settings such as `stealth_mode`, `run_in_background`, `click_gap`, and other behavior toggles.

Validate settings before running; the bot includes a validator that checks common configuration issues.

## Run

Activate your virtualenv and run:

```bash
source .venv/bin/activate
export SSL_CERT_FILE="$(python -m certifi)"  # macOS only if needed
python runAiBot.py
```

The bot will open a Chrome session (guest profile by default if configured) and attempt to log in. If automatic login fails, follow the on-screen instructions to sign in manually and confirm.

## Contributor guidelines

- Open a pull request for changes and follow the repository's contribution workflow.
- Keep changes focused and include tests or a short verification procedure when applicable.
- Use the issue tracker for bug reports and feature requests.

## Major updates history

See the `CHANGELOG.md` (if present) or the commit history for detailed change records.

## Disclaimer

This software is provided for educational purposes. Use at your own risk. The maintainers are not responsible for misuse or any consequences arising from its use. Review and follow LinkedIn's terms before running automated tools against their site.

## License

Copyright (C) 2024 Auto Job Applier contributors

This program is licensed under the GNU Affero General Public License v3 (AGPLv3). See the `LICENSE` file for details.

## Community & Support

For repository discussion and support please use GitHub Discussions and Issues:

- https://github.com/GodsScion/Auto_job_applier_linkedIn/discussions
- https://github.com/GodsScion/Auto_job_applier_linkedIn/issues

[back to the top](#linkedin-ai-auto-job-applier-)
