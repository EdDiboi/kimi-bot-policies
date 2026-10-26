# Kimi bot policies

Updated October 26, 2026. These pages cover the Kimi Discord bot and its privacy controls.

[Privacy Policy](PRIVACY.md) · [Terms of Use](TERMS.md)

In Discord, `/privacy info` provides the GitHub policy link. The instructions below explain the controls available in Discord.

## Your privacy controls

Run these commands in Discord:

- `/privacy optout` stops Kimi from processing your messages and restricts posting in the AI conversation channel. Your support tickets stay open.
- `/privacy optin` turns processing back on and restores the channel permissions Kimi changed. You can also use the **Opt Back In** button after opting out.
- `/privacy delete` clears temporary AI context, deletes your tracked support tickets, and opts you out. A small encrypted record remains so Kimi can keep respecting that choice.

Opt-out applies to ordinary replies and `/ask`. It does not restrict unrelated channels. Server owners and administrators can bypass Discord's posting restrictions, but Kimi still excludes their messages while they are opted out. Opting back in does not remove other moderation restrictions or recover deleted context.

## Get help or make a data request

1. Run `/help` in the configured server.
2. Press **▶** twice to reach the support page.
3. Choose **Open a ticket**, describe the issue, and submit the form.

The help menu is private to you. The bot grants access to the hidden support channel when your ticket is created. The ticket is a private Discord thread for you, the configured operators, and staff who can manage private threads. Its text is never sent to the AI.

Closing a ticket keeps its messages. To reopen or delete a closed ticket, run `/privacy tickets` in the support parent channel and use the returned controls. Deletion asks for confirmation.
