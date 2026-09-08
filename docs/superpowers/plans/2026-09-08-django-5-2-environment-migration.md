# Django 5.2 Environment Migration Implementation Plan

> **For agentic workers:** Implement each task in order and preserve the module-one prohibition on AI-generated test cases and automated tests.

**Goal:** Run the imported Campus Fresh baseline reproducibly on Python 3.13 and Django 5.2 LTS.

**Architecture:** Preserve all four legacy Django apps and their URL shapes. Limit changes to dependency, framework-compatibility, local configuration, and startup documentation so later business defects remain available for the team’s testing work.

**Tech Stack:** Python 3.13, Django 5.2.17, django-tinymce 5.0.0, Pillow 12.3.0, SQLite

**Spec:** `docs/superpowers/specs/2026-09-08-django-5-2-environment-migration-design.md`

## Global Constraints

- Modify only `E:\project\softtest project`.
- Treat `E:\project\soft_test` as read-only reference material.
- Do not generate module-one test cases or automated tests.
- Do not fix unrelated business defects in this migration.

### Task 1: Pin the runtime

- [x] Pin Python 3.13 in `.python-version`.
- [x] Pin Django 5.2.17, django-tinymce 5.0.0, and Pillow 12.3.0.
- [x] Create `.venv` and install the pinned dependencies.

### Task 2: Replace removed Django APIs

- [x] Replace `django.conf.urls.url` with `django.urls.re_path`.
- [x] Replace `request.is_ajax()` with the `X-Requested-With` header check.
- [x] Replace `{% load staticfiles %}` with `{% load static %}`.
- [x] Use Django’s debug static helper for uploaded media.

### Task 3: Modernize local settings

- [x] Correct the SQLite `OPTIONS` nesting.
- [x] Make secret key, debug mode, and allowed hosts environment-configurable.
- [x] Remove the deleted `USE_L10N` setting and preserve legacy primary-key types.
- [x] Update TinyMCE configuration for the current package.

### Task 4: Verify and document

- [x] Run Django system checks.
- [x] Apply migrations to a clean ignored SQLite database.
- [x] Confirm no model migration is pending.
- [x] Start the development server and make a local HTTP request.
- [x] Update README with exact setup commands and verified limitations.
- [ ] Review the diff, commit the migration separately, and push it to `main`.
