# PorchLyte AI Agent Foundation

The personalization layer for the PorchLyte AI Agent system, distributed as an installable Claude plugin. Instead of downloading and uploading a zip, you add this marketplace once and Claude installs (and updates) the plugin for you.

This is **step one**. You set up your Foundation first. Later — usually another day, so you're not doing everything at once — you add the [AI Agent Team](https://github.com/PorchLyte/porchlyte-agents), and every team member reads from the Foundation you build here.

This marketplace holds one plugin:

- **AI Agent Foundation** — three skills (Voice, Brand, Local) that teach Claude how you sound, how your brand looks, and what your market is really like. Everything in the Team reads from it.

## How to install (for agents using these)

In the Claude desktop app, you add this marketplace through the Plugins panel (not a chat command):

1. Open the left sidebar, click **Customize**, then the **Plugins** tab.
2. Click **Add** (top right), choose **Add marketplace**, and paste in:

   ```
   PorchLyte/porchlyte-foundations
   ```

   > The pattern is always `owner/repo`. Replace `PorchLyte` if this repo moves.
3. Under the new **porchlyte-foundations** marketplace, find **AI Agent Foundation** and click **+** to install it.

Then set up your Foundation by typing this slash command in a chat:

```
/foundations-setup
```

That walks you through Voice, Brand, and Local one at a time (about 15–20 minutes for all three). You can stop after one and come back later. Your answers save.

> Note: `/plugin marketplace add` and `/plugin install` are Claude **Code** (CLI) commands. They do **not** work in the Cowork desktop app, where you install through the Plugins panel above. Only commands that come from an installed plugin (like `/foundations-setup`) work as slash commands in Cowork.

When you're ready for the team, head to the [AI Agent Team repo](https://github.com/PorchLyte/porchlyte-agents) and run `/set-me-up`.

## How updates work

Once someone has added the marketplace, they get your latest version automatically. When you push a change to this repo, their Claude picks it up the next time it refreshes the marketplace. To pull updates immediately, in **Customize > Plugins** they click the **···** next to the **porchlyte-foundations** marketplace and choose **Update**.

No new zip. No re-uploading. You edit here, they get it there.

## How to update the plugin (for Tracy)

1. Edit the files inside `plugins/ai-agent-foundation/`.
2. Commit and push to GitHub.

That's it. Because the plugin doesn't pin a version number, every commit you push counts as a new version, so your users receive the update on their next refresh.

If you'd rather control exactly when updates go out, add a `"version"` field to `plugins/ai-agent-foundation/.claude-plugin/plugin.json` and bump it on each release. Then users only update when that number changes.

## Repo layout

```
.claude-plugin/marketplace.json     <- the catalog that lists the Foundation plugin
plugins/
  ai-agent-foundation/              <- Foundation plugin (Voice, Brand, Local)
```

## License & access

Proprietary. All rights reserved. This is **not** open source. Use requires a current paid license or subscription from PorchLyte — see [LICENSE](LICENSE). Do not copy, share, redistribute, or resell. (The repo is public for now only so customers can install; private access is planned.)

## Questions

Email tracy@porchlyte.com or visit porchlyte.com.

— Tracy
