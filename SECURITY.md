# Security policy

## Reporting a vulnerability

Report vulnerabilities privately through GitHub private vulnerability
reporting: open this repository's **Security** tab and choose **Report a
vulnerability**. Do not open a public issue or pull request for a security
problem.

This repository holds only the marketplace catalogue. A vulnerability in the
catalogue itself — for example an entry pinning a commit it should not, or
pointing at the wrong source — belongs here. A vulnerability in a plugin's own
code belongs in that plugin's repository, listed in the README.

## Supported versions

The catalogue is served from `main`, so fixes land on `main` only. Earlier
tags and commits are not patched.
