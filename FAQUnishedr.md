FAQ Unishedr

1. What does unishedr_bot.py do?
It launches a Discord Gateway connection (via WebSocket) and an aiohttp server on port 5000 to receive Ko‑fi webhooks. Once both are running, it registers all feature modules at startup.

2. How does Ko‑fi integration work?
Incoming POSTs to /kofi-webhook are parsed by KoFiClient. For each guild where the bot is present, it checks member count against predefined tiers (0–500, 501–2000, 2001–10000), then posts a notification in the designated channel showing donor name, amount, and applicable tier price.

3. What are “tiers”?
A simple list of dictionaries maps a guild’s member count to a monthly price:

0–500 → $0/mo

501–2000 → $8/mo

2001–10000 → $15/mo
Tiers determine how much a server would pay if using Ko‑fi to unlock dashboard features.

4. What does modules/moderation.py offer?
Group commands under !mod:

ban / kick to remove members

mute / unmute to silence via a “Muted” role

warn to issue a textual warning

5. What does modules/reminder.py provide?
Two scheduler‑backed commands:

!remindme <minutes> <message> schedules a one‑off alert after X minutes

!exam <YYYY-MM-DD> <subject> fires on the exam date with a subject reminder

6. What does modules/economy.py handle?
Maintains per‑user balances in a JSON file:

!balance shows your wallet

!work grants $10

!pay @user <amount> transfers funds if you have enough

7. What does modules/music.py enable?
Voice‑channel audio using YouTube:

!join connects the bot

!play <YouTube URL> streams best‑quality audio

!leave disconnects

8. What does modules/polls.py create?
Embed‑based polls via !poll "Question" "Option1" "Option2" …. The bot posts an embed and adds number‑emoji reactions so members can vote easily.







