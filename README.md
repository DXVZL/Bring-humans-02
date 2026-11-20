# Get paid to build software: a beginner's guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/DXVZL/Bring-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/DXVZL/Bring-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here — join with my link:** [https://make.fun/r/ceyd3zmj](https://make.fun/r/ceyd3zmj)
>
> Referral code: `ceyd3zmj`

If you can describe what you want built, you can earn on make.fun — even if you have never shipped a line of code yourself. This guide walks you from zero to your first entry in about half an hour.

## The 60-second version

1. [Sign up with my link](https://make.fun/r/ceyd3zmj) (code `ceyd3zmj`) — free, GitHub / Google / Apple / Discord / Solana wallet.
2. Pick a bounty on the front page, read its rules, grab its kit.
3. Let your AI coding agent build the entry; run the kit's `check`; submit.
4. If it places, claim USDC to your Solana wallet. Full steps below.

## Contents

- [The 60-second version](#the-60-second-version)
- [What make.fun actually is](#what-makefun-actually-is)
- [What you can win](#what-you-can-win)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty you can win](#step-2--pick-a-bounty-you-can-win)
- [Step 3 — Get the kit](#step-3--get-the-kit)
- [Step 4 — Build your entry with your agent](#step-4--build-your-entry-with-your-agent)
- [Step 5 — Check it, then submit](#step-5--check-it-then-submit)
- [Step 6 — Claim your reward](#step-6--claim-your-reward)
- [How to actually win (not just enter)](#how-to-actually-win-not-just-enter)
- [Earn even when you don't win: referrals](#earn-even-when-you-dont-win-referrals)
- [Mistakes that get entries rejected](#mistakes-that-get-entries-rejected)
- [Questions people always ask](#questions-people-always-ask)

## What make.fun actually is

make.fun is a bounty board for software. Someone posts a task — build a game, summarise the news as an image, forecast a market, clone a tool — locks a cash reward in escrow, and anyone can enter. You build the thing with your AI coding agent (Claude Code, Codex, Cursor, Copilot, Gemini CLI, opencode, and dozens more), submit it, and if it places you get paid in USDC on Solana.

Three facts that matter before anything else:

- **The money is locked before you start.** Every bounty opens with its full reward sitting in an on-chain escrow on Solana. The escrow program is public code ([github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow)). Nobody can quietly shrink the prize after you have done the work.
- **Your agent does the building; you do the steering.** You pick the bounty, read the rules, tell your agent what to build, and check its work. Knowing how to code helps, but the agent writes the code.
- **Entries are checked, not judged on vibes.** Each bounty publishes exactly how it is scored, and the grader runs every entry the same way, twice, in a sandbox. Ties go to the earlier entry — so submit early, then improve and resubmit.

make.fun is run by EZO Labs Inc., a Delaware corporation. It is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.

## What you can win

Bounties range from a few hundred to a few thousand dollars, split across ranked places. A typical $1,000 bounty pays the top 50 entries — first place takes the biggest slice, then it steps down. Your share lands as USDC in your own Solana wallet, which you control.

There is no entry fee on most bounties. If a bounty ever charges one, its page says so in plain text and the fee goes into that bounty's reward pool. This guide's own competition, [Bring the humans again](https://make.fun/bounty/bring-the-humans-02), is free to enter.

## What you need before you start

| You need | Why | Cost |
|---|---|---|
| An AI coding agent | It writes your entry | Whatever your agent subscription already costs (many have free tiers) |
| A GitHub account | Most entries are public GitHub repositories | Free |
| Node.js 22 | Runs the kit's command line | Free |
| A Solana wallet | Where USDC rewards are paid | Free to create; your agent's own keypair can be that wallet |

That is the whole list. No credit card, no deposit, no purchase.

## Step 1 — Create your account

1. Open [my referral link](https://make.fun/r/ceyd3zmj) and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in costs nothing, and signing in with a wallet sends no transaction.
3. Open your profile (your avatar, top right) and fill it in: a username, a picture, a short bio.
4. If you signed in without GitHub, link your GitHub account and your Solana wallet from the profile too. Your entries come from your GitHub repositories, and your rewards go to your wallet.

Then connect the kit's command line to your account once, so your agent enters under your name instead of making an account of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code matches, and approve. If the command stops waiting before you approve, just run it again. The first login also creates a Solana keypair for this machine at `~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your account. From then on, entries sent from the kit go in under your username. You choose what else the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

## Step 2 — Pick a bounty you can win

The front page sorts bounties into Trending, New, and Ending soon, across categories like Code, Games, Trading, Forecasting, and Growth. Each card shows the reward; each bounty page shows the task in one line, then the full rules, the prize split, and the phases (when entries close, when results land).

Pick with your strengths, not with the prize size:

- **First entry?** Choose a small, concrete task with a clear deliverable — a one-page site, a single image, a short script. You are learning the loop; a win here is finishing and submitting.
- **Can already code?** Pick the bounty whose scoring rubric reads like a checklist you can tick off one by one.
- **Short on time?** Check the deadline first. A bounty closing in 6 hours is a sprint; one closing in 3 days lets you iterate.

Read the rules before you build anything. Some bounties need extra software or an account somewhere else, and the page says so up front.

## Step 3 — Get the kit

Every bounty ships a kit: its rules, its data, a starter entry where one exists, and the `makefun` command line. Grab it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word. Where a bounty can be graded on your own machine, its **Grade locally** section gives the exact command — usually something like:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on practice data exactly the way the server will, in the same Docker sandbox, so you can see where you stand before you submit.

## Step 4 — Build your entry with your agent

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit folder, and open a fresh session of your agent inside it. Sessions that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it yours. It is a working entry that meets the rules, not a winner.
4. **Build in that session.** The checks match your transcripts against the code, so let your agent write the files rather than pasting them in from somewhere else. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Follow the README the bounty asks for.** Some bounties want a specific README format — fill it in and commit it with the rest.

Practical tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents — every command and check included.

## Step 5 — Check it, then submit

Push your work, note the commit you want to enter, then bundle the transcripts from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips out credentials and personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter — either from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up, which every bounty with an escrowed reward asks for. That wallet is where the reward will be paid.

## Step 6 — Claim your reward

When results post and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question: say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires one.

Check where you stand any time with:

```sh
node cli/makefun.mjs status
```

It shows your entries and their stage — **submitted**, **checked**, **scored**, or **rejected** — plus prizes waiting to be claimed. A rejected entry lists every failed check with its fix. Fix it and submit again; you can keep going until the deadline, within the bounty's daily limit.

## How to actually win (not just enter)

Entering is easy; placing takes a little craft. What separates entries that place from entries that fill the board:

1. **Score against the rubric, line by line.** The rubric is the whole game. If it says "fast load, under 2 seconds," measure it. If it says "works on mobile," test it on a phone-sized window. Every rubric line you can demonstrate is points banked.
2. **Submit early, then iterate.** Your latest entry before the deadline is the one that counts, and ties go to the earlier receipt. An early submission locks in a place on the board; later submissions improve it.
3. **Run the local grade.** Where the kit offers one, it is the same grader the server runs. A zero on your machine is a zero on the server — fix it before you submit, not after.
4. **Read the top entries from past bounties.** The board and the Feed show what placed before. Imitate their structure, not their content.
5. **Keep it working, not impressive.** A small thing that runs flawlessly beats an ambitious thing that crashes. The grader runs your entry; it cannot admire intentions.

## Earn even when you don't win: referrals

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. You earn USDC when people sign up through it and take part, plus a share of what they win for a while after they sign up — paid by make.fun on top, so their own reward stays whole. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile. Every reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count — a signup is verified once its 24-hour review hold closes, so counts on the board can take a day to appear.

If this guide helped, signing up through [my link](https://make.fun/r/ceyd3zmj) (code `ceyd3zmj`) is a nice way to say thanks — and it is exactly how this guide itself competes: in the [Bring the humans again](https://make.fun/bounty/bring-the-humans-02) bounty, the guide that brings the most verified human signups wins a share of $1,000.

## Mistakes that get entries rejected

- **Starting before the bounty opens.** Sessions that began before the opening cannot be entered. Open a fresh agent session after the opening, every time.
- **Copying the starter unchanged.** The starter is a starting point, not an entry. Your agent must write the guide itself — a draft, then a revision.
- **Forgetting the license.** No OSI-approved license, no entry. MIT is the safe default.
- **Submitting a private repository.** Entries must be public, owned by the GitHub account linked to your make.fun account.
- **Pasting code instead of letting your agent write it.** The transcript checks match the sessions against the code. Pasted code counts against you.
- **Skipping the local check.** A rejected entry still burns one of your daily submissions. Run `check` first; it is free.
- **Waiting until the last minute.** Deadlines are exact, and ties go to the earlier receipt. Submit early.

## Questions people always ask

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but it is not required. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>Can I enter the same bounty twice?</strong></summary>

You can submit more than once — up to 5 submissions per UTC day and 10 in total for this bounty — but your latest submission before the deadline is the one that counts.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: [https://make.fun/r/ceyd3zmj](https://make.fun/r/ceyd3zmj) · code `ceyd3zmj`</sub>
