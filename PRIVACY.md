# Kimi Discord Bot Privacy Policy

Updated October 26, 2026.

Kimi is an AI conversation bot for Discord. This page explains what this bot uses, where the data goes, and how to control it. It does not replace Discord's or Moonshot AI's own policies.

## Stop processing, opt back in, or delete data

Use these commands in Discord:

- **`/privacy optout`** stops future AI processing of your messages, clears the bot's temporary conversation context, and cancels pending AI replies. In the configured server, Kimi also gives you its opt-out role and blocks sending messages, creating threads, and sending in threads under the AI conversation channel. Support tickets and other channels stay available.
- **`/privacy optin`** allows processing again and restores the permission changes Kimi recorded making. The **Opt Back In** button shown after opting out does the same. Kimi removes the opt-out role only if it added it. Other moderation restrictions still apply, and old context is not recovered.
- **`/privacy delete`** clears temporary conversation context, cancels pending AI replies, deletes your tracked bot-created support tickets, and opts you out. It keeps only the preference and permission-restoration records needed to honour that choice, plus any references needed to retry incomplete deletion.

The processing refusal applies to both automatic replies and `/ask`. Server owners and administrators can bypass Discord's channel restrictions, but Kimi still blocks AI processing for opted-out accounts. If a permission change fails, the bot keeps the processing refusal and tells you that access restoration or deletion needs attention. A pre-existing opt-out role may need a moderator to remove it before you can opt back in.

These controls do not delete your ordinary Discord messages or recall data already received by an AI provider. `/reset` clears only the current channel's temporary AI context. Privacy deletion and opt-out clear context across the bot's channels because other replies may refer to your messages.

## When Kimi reads messages

This edition uses one configured server for AI and support. Kimi answers ordinary messages in its selected AI channel and explicit `/ask` requests elsewhere in that server. `/ask` is refused outside the server and in the support channel, its child threads, and tracked tickets.

An authorised operator with Manage Server permission selects the channels and opt-out role. The bot needs a public policy link and completed privacy setup before AI processing starts. The AI channel has a processing notice, and `/ask` displays a notice before sending its request. Kimi does not bulk-fetch old messages, monitor presence, or request the Guild Members privileged intent.

Opted-out messages are excluded from AI requests and conversation history. The bot still receives the Discord events needed to recognise the account and apply its preference. If a channel already has an AI request running, new ordinary messages there are skipped rather than queued.

## What goes to Moonshot AI

To answer an eligible request, Kimi sends the message text, supported images, recent channel context, and the current speaker's display name and role names to Moonshot AI's API over HTTPS. The bot does not automatically add the speaker's raw Discord user ID to the AI prompt. A message itself may contain identifying information, so avoid submitting secrets or sensitive personal details.

Context is shared within a channel. An answer can refer to another participant's earlier message. If a web search is needed, a generated query goes to Moonshot AI's Search Pro service and may include details from the conversation.

The bot uses the model to generate replies and does not train or fine-tune models. Moonshot AI's [API FAQ](https://www.kimi.com/en/help/kimi-api/api-data-security) states that API inputs and outputs are not used for model training. This policy does not promise a provider retention period or claim that a Discord command deletes provider-held copies.

## How long conversation context lasts

Conversation history stays in the running bot's memory. It is not written to the encrypted settings file or saved as a conversation or image archive. The window holds up to 24 previous user and final-reply messages plus the incoming message. Older complete turns are discarded as new ones arrive. System instructions and intermediate search, tool, and reasoning records are additional to that visible-message count.

Each turn expires after 24 hours, even in an inactive channel. The bot excludes expired turns before reuse and checks for cleanup each minute. It retains at most 100 conversation channels and disables Discord's separate message cache. Restarting clears the conversation history.

The `/help` menu keeps only its navigation state in memory, including your Discord ID, server ID, current page, and a temporary reference. That state expires after ten minutes and is cleared by `/privacy delete`. Ticket descriptions are not kept in the menu state.

## Saved data and security

The bot saves the configuration, opt-out preferences, ticket references, and prior permission settings it needs to run and restore access. These records can contain user, server, role, channel, and ticket IDs; timestamps; ticket claim and closed status; custom bot instructions; and the permission bits changed by the bot. They are encrypted with AES-256-GCM. The encryption key is managed separately from the state file and excluded from source control. Hosting backups may have their own retention.

Opt-out and restoration records stay until you opt back in and restoration succeeds, or the operator handles a further removal request. Temporary access granted to the hidden support channel is recorded so the bot can restore it after your last ticket is deleted. Failed cleanup can leave a reference pending for retry. Configuration stays until it is replaced or the deployment is removed.

Application logs use fixed operational codes and do not intentionally contain message text, attachment URLs, search queries, user identifiers, provider responses, or credentials. Hosting infrastructure and AI services have separate operational records and retention. Discord handles messages and interactions under [Discord's Privacy Policy](https://discord.com/privacy).

## Support tickets and data requests

To report a problem, abuse, a security issue, or a request about your data:

1. Run **`/help`** in the configured server.
2. Press **▶** twice.
3. Select **Open a ticket**, enter up to 1,000 characters, and submit.

The menu and its replies are visible only to you. The bot grants you access to the otherwise hidden support channel, creates a private thread, and invites you and the configured operators. Staff with Manage Threads or Administrator permissions can also read private tickets. Do not include passwords, access tokens, or unnecessary personal information.

Ticket text stays on Discord. It is never added to the AI conversation, sent to the model, or saved as a local report archive. Before posting the initial report text, Kimi saves an encrypted reference so it can find and delete the thread. The bot tracks at most 100 tickets overall and five per user. Operators review tickets and handle requests there.

An operator can claim a ticket. You or an operator can close and reopen it. **Closing locks and archives the thread; it keeps the messages.** Use `/privacy tickets` in the support parent channel for Reopen and Delete controls, including for archived tickets. `/privacy reopen reference:<ticket reference>` can reopen your ticket from that channel. The Delete button asks for confirmation; operator-only `/privacy resolve` also deletes the thread. Opt-out keeps tickets, while `/privacy delete` removes your tracked tickets.

The bot attempts to delete tickets 30 days after creation. Closing or reopening does not restart that period. Cleanup runs while the bot is online and when it starts. Offline periods, lost permissions, or Discord failures can delay deletion and require operator action. References are retained when needed to retry. After your last tracked ticket is deleted, the bot restores the support-channel access it changed. Discord's own retention and independently copied messages are outside this deletion process.

If a command reports incomplete deletion or restoration, retry it or ask a server administrator or bot operator for help. Ordinary Discord posts must be managed through Discord's own controls. Requests involving provider-held data may need to be referred to that provider.

## Policy changes

This page will be updated when the bot's data handling changes. Changes must be reflected in the bot's notices and published policy before the new processing takes effect.
