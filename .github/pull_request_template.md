Post-merge checklist:

The master branch is auto-deployed to `dash.plot.ly`.
Once you have merged your PR, wait 5-10 minutes and check dash.plot.ly
to verify that your changes have been made.

- [ ] I understand

If this PR documents a new feature of Dash:

- [ ] Comment on the original Dash issue with a link to the new docs.
- [ ] Reply to any community thread(s) asking for this feature.

If this PR includes a new dataset available at a remote URL:
- [ ] I have added this dataset to the `datasets/` folder
- [ ] I have added a mapping between the remote URL and the filename in the
`datasets/` folder into the `find_and_replace` dict in `dash_docs/tools.py`

If this PR adds an image or animated GIF:
- [ ] This image was saved and referenced locally rather than via an external link

If I introduced a new relative link inside `dcc.Markdown`:
- [ ] I considered whether I could replace the `dcc.Markdown` call with `reusable_components.Markdown`, which will replace relative links with `tools.relpath` internally. Otherwise, I used e.g. `<dccLink href=tools.relpath('/getting-started') children="the first chapter"/>` instead of `[the first chapter](/getting-started)` (importing `tools` from `dash_docs`), and set `dangerously_allow_html=true` in the `dcc.Markdown` call.
