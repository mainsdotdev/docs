# Mains documentation instructions

## Project

- This is the public Mains documentation site, built with [Mintlify](https://mintlify.com).
- Content is English MDX with YAML frontmatter. Configuration and navigation live in `docs.json`.
- The sibling `../mains` repository is the source of truth for product behavior. Read its relevant instructions and implementation before describing a feature.
- For Mintlify components, configuration, and writing standards, use the Mintlify skill: `npx skills add https://mintlify.com/docs`.

## Terminology

- **Mains** is the product; use **Code**, **Work**, and **Chat** for its user-facing modes. `developer` is an internal identifier for Code.
- A **space** selects an agent provider, mode, and instructions. A **project** groups Code repositories; a **workspace** is a working directory within a Code project.
- Work and Chat use **collections** internally, shown as **Projects** in their sidebar. Explain that distinction when relevant.
- A **run** holds conversation history and tool activity. A **turn** is one user request and the agent's response.
- **Atlas** is the shared library. **Pages** are editable native documents; generated files and saved copies have different lifecycles.
- Use **Mains Connect** for remote backend connections. Retain existing `/relay/*` documentation paths for compatibility.
- Distinguish agent authentication, service connections, and Git/`gh` authentication.
- Distinguish local synced issue context, live GitHub PR reviews, and unpublished workspace review comments.

## Writing

- Use active voice and second person. Keep sentences concise, with one idea per sentence.
- Use sentence case for headings. Use bold for UI controls and code formatting for commands, paths, file names, and code references.
- Give every page a descriptive title and description. Use built-in Mintlify components when they improve the explanation.
- Use root-relative internal links. Add every new user-facing page to navigation.
- Lead with the user's task, then explain setup, behavior, and material limits. Keep implementation details in the maintainer README unless they help the user act.

## Scope and accuracy

- Document shipping user-facing behavior across desktop, web, server, and mobile. State client and provider differences where they matter.
- Do not present planned features, marketing previews, or removed agent tools as available functionality.
- Verify defaults, permission rules, archive/delete behavior, persistence, and scheduling against code. Do not infer guarantees from a feature name.
- Explain local storage and provider data flow precisely. Avoid blanket claims that all data stays on the device or that every credential is encrypted on every backend.
- Preserve existing page URLs. Audit references from `https://mains.dev`, including product pages and release posts, when restructuring.
- Keep existing local source changes intact. Documentation work does not authorize changing the sibling product implementation.

## Verification

- Run `mint validate` and `mint broken-links` after content or navigation changes.
- Run `git diff --check` and inspect the local `mint dev` preview for substantive layout changes.
- Check navigation coverage and website-linked documentation paths. Record the audited product revision in `README.md` when doing a broad refresh.
