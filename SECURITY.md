# Security Policy

This policy applies to every public repository in the [g-udi](https://github.com/g-udi) organization that does not define its own.

## Supported Versions

Only the latest commit on the default branch (`main`) of each repository is supported. Fixes are not backported to older tags.

## Reporting a Vulnerability

Please do not open a public issue, pull request, or discussion for a security problem.

Report it privately through GitHub's private vulnerability reporting, on the repository that is affected:

1. Open the affected repository on GitHub.
2. Go to the **Security** tab.
3. Choose **Report a vulnerability** and fill in the form.

See GitHub's guide on [privately reporting a security vulnerability](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability) for details.

A useful report includes:

- The repository and the file, command, or widget involved.
- What an attacker could do and under which conditions.
- Steps to reproduce, or a minimal proof of concept.
- The operating system and shell (or Übersicht/SketchyBar version) you used.

## Exposed Credentials

If you find a token, API key, or other credential in a repository or its history, report it the same private way and do not copy the value into the report: the file path and commit are enough.

## What to Expect

Reports are read and acknowledged in the private advisory. Once a fix is ready it lands on the default branch and the advisory is published with credit to the reporter, unless you prefer to stay anonymous.
