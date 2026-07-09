# Troubleshooting Guide

# Issue 1

## Docker Daemon Not Running

Error:

```text
failed to connect to dockerDesktopLinuxEngine
```

Root Cause:

Docker Engine unavailable.

Fix:

Start Docker Desktop.

---

# Issue 2

## Docker Build Context Missing

Error:

```text
docker buildx build requires 1 argument
```

Root Cause:

Build context not supplied.

Wrong:

```bash
docker build -t flask-app:v1
```

Correct:

```bash
docker build -t flask-app:v1 .
```

---

# Issue 3

## Dockerfile Not Found

Error:

```text
failed to read dockerfile
```

Root Cause:

Dockerfile missing or incorrect name.

Fix:

```text
Dockerfile
```

must exist.

---

# Issue 4

## Git Push Rejected

Error:

```text
non-fast-forward
```

Root Cause:

Remote history differs.

Fix:

```bash
git pull
```

then push.

---

# Issue 5

## Pipeline Option Missing

Observation:

Only Freestyle Project available.

Investigation:

Checked plugins.

Finding:

No Pipeline plugins installed.

Root Cause:

Incomplete plugin installation.

---

# Issue 6

## Jenkins Plugin Installation Failure

Error:

```text
java.net.SocketTimeoutException
```

Findings:

- Browser access successful
- Jenkins URL access successful
- Plugin installation failed

Further Investigation:

Plugin directory contained:

```text
82 .jpi.tmp files
```

All:

```text
0 bytes
```

Root Cause:

Plugin downloads never completed.

Impact:

```text
Git Plugin unavailable
Pipeline Plugin unavailable
Workflow Plugins unavailable
```

---

# Issue 7

## Execute Shell on Windows

Error:

```text
Cannot run program "sh"
```

Root Cause:

Linux shell used on Windows.

Fix:

```text
Execute Windows batch command
```

---

# Issue 8

## pytest Command Not Found

Error:

```text
pytest is not recognized
```

Root Cause:

PATH issue.

Fix:

```cmd
python -m pytest
```

---

# Issue 9

## Container Deployment Failure

Error:

```text
No such container: flask-app:
```

Root Cause:

Typographical error.

Invalid:

```text
flask-app:
```

Correct:

```text
flask-app
```

---

# Troubleshooting Methodology

Always follow:

## Symptom

What failed?

## Evidence

What logs prove it?

## Root Cause

Why did it happen?

## Resolution

How was it fixed?

## Prevention

How can recurrence be avoided?

This methodology is more important than any individual command.
