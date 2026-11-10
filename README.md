# MRANTI Memo Studio

A standalone staff memo form based on the structure of the supplied MRANTI memo. No installation, API key or build step is needed. Open index.html to try it.

## Publish on GitHub Pages
1. Create a GitHub repository, for example `mranti-memo`.
2. Upload index.html, style.css and app.js to its root. Upload the extracted files, not the ZIP.
3. In Settings > Pages, select Deploy from a branch, then main and /(root), and Save.
4. Open the Pages URL shown by GitHub after deployment.

## Staff workflow
Fill required routing and narrative fields. Add budget details and sign-off names. Generate the memo, review and edit the preview, then Print / Save PDF or Download editable HTML. The HTML download captures preview edits and can be opened in a browser or imported into Word/Google Docs (formatting can vary).

Save form draft downloads JSON containing only form inputs; it does NOT contain manual preview edits. Download editable HTML to preserve those edits. Load form draft restores JSON inputs. Nothing is automatically saved or uploaded. Closing the tab loses unsaved work.

## Scope
This is a functioning template-based first version, not a connected AI assistant. It preserves the sample's section structure, not its exact branded layout. It does not copy historical memo content, policy thresholds, signatures, approval decisions or employee lists. Optional empty sections are omitted. A complete budget calculates allocation minus spent minus requested amount; missing figures are not assumed to be zero. Negative balance triggers a warning.

No staff login, central archive, automatic reference numbering, Google Docs creation, electronic signatures or approval routing is connected. The public website contains only blank form code. Do not commit completed memos or staff data to the repository. A public Pages URL is not staff access control.

## Add AI and Google Docs in phase 2
Keep the form on GitHub Pages and add an authenticated backend. The backend should validate staff identity, hold the AI key in server secrets, enforce request limits, use approved fixed writing instructions, and return a structured draft. Staff review the draft before export or submission. Never put an AI API key in the public JavaScript or repository.

For Google Docs output, the backend can copy an approved blank Google Docs template and replace defined placeholders. Authenticate using an organisation-approved Google integration. Keep originals, permissions and generated copies in the appropriate restricted Drive folder. Configure actual staff authentication and authorisation before sending internal memo content to a backend.

Suggested fixed drafting instructions: Use professional Malaysian English. Preserve all provided names, figures and dates. Do not invent policy clauses, approvals, quotations or supporting evidence. Mark missing information for the author. Generate a draft only; never assert approval has been granted.

## Customisation
Edit the groups array in app.js to change form labels. The build function controls memo sections. Colours and print styles are in style.css. No third-party assets, analytics or network dependencies are used.

## Validation
JavaScript syntax and generation logic checked. Browser layout and PDF pagination must be checked in your target browser before rollout.
