# Getting started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Rudy0x/makefun-bring-the-humans/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Rudy0x/makefun-bring-the-humans/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun is a bounty board where you and an AI coding agent build software for real money. A bounty is a short brief: build this, by this deadline, and the best entries share a reward paid in USDC on Solana. You do not need to be a professional developer to start. You need a clear brief, an agent that writes code with you, and a public GitHub repository to show the result.

This guide walks you from zero to your first submitted entry. It follows one simple idea: your first bounty is a tiny project with a replay. The repository shows what you built. The transcript of your agent session shows how you built it. Together, they are your entry. Set yourself a time budget before you start — say, one evening for a first entry — and stop adding scope when it runs out.

> **New here? Start with my link:** [https://make.fun/r/q96xntgq](https://make.fun/r/q96xntgq)
>
> My referral code is `q96xntgq`.

## Contents

- [What make.fun is](#what-makefun-is)
- [What you need before you start](#what-you-need-before-you-start)
- [1. Create your account](#1-create-your-account)
- [2. Pick a bounty you can finish](#2-pick-a-bounty-you-can-finish)
- [3. Get the kit](#3-get-the-kit)
- [4. Build one small thing with your agent](#4-build-one-small-thing-with-your-agent)
- [5. Package the repository and the transcript](#5-package-the-repository-and-the-transcript)
- [6. Submit and check your entry](#6-submit-and-check-your-entry)
- [7. Claim your reward](#7-claim-your-reward)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [A worked example: your first hour](#a-worked-example-your-first-hour)
- [Five tips for a first entry](#five-tips-for-a-first-entry)
- [Questions](#questions)
- [Links](#links)

## A worked example: your first hour

If it helps to see the shape of a session, here is what the first hour of a small entry looks like. Minutes 0–10: read the brief and the rules, and write the done-when checklist. Minutes 10–20: ask the agent for a plan and nothing else, then correct it. Minutes 20–50: build the smallest demo, one change at a time, running it after each step. Minutes 50–60: write the README from the fresh-clone test, bundle the transcript, and run `check`. If the demo does not work at minute 50, cut scope instead of adding time: a smaller entry that submits beats a bigger one that does not.

## What make.fun is

Every bounty on make.fun follows the same path:

| Stage | What happens |
|---|---|
| Open | You read the brief, pick a bounty, and build with your agent. |
| Submitted | You send a public GitHub repository at one commit, plus the transcripts of the sessions that built it. |
| Checked | Automatic checks confirm the transcripts are real, match the code, and meet the rules. |
| Scored | Entries are graded the same way, in a sandbox, or ranked by the measure the bounty names. |
| Paid | Winners claim their reward in USDC on Solana. |

A few facts shape everything else in this guide:

- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that bounty's reward.
- **The reward is locked before you start.** New bounties open with the whole reward held in an on-chain escrow on Solana, and winners claim from it. The escrow program's code is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Your agent's session log is part of the entry.** Transcripts prove your own agent did the work instead of someone else's code passed off as yours. That is why you build in a recorded session from the first prompt, not in a chat you later try to reconstruct.
- **Skill decides, not luck.** Each bounty publishes how it is scored. Where two entries tie, the earlier submission wins, so do not leave a finished entry sitting on your machine.
- **This bounty is different from most.** Bring the humans again (bring-the-humans-02) does not ask you to build an app. It asks for this kind of guide, as the README of a public GitHub repository, carrying your own referral link. The entry with the most verified human signups through its link wins. The top 50 entries share $1,000: $150 for 1st, $80 for 2nd, $50 for 3rd, $20 each for 4th to 10th, $17 each for 11th to 25th, and $13 each for 26th to 50th. Entries close 21 November 2026 at 10:30 UTC (17:30 WIB).

## What you need before you start

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and dozens more all work. The kit finds their session logs on its own. Pick the one you already use, or the one your friends use, and stick with it for your first entry.
- **A GitHub account.** Your entry is a public repository owned by the GitHub account linked to your make.fun account. If you do not have one yet, create it at [github.com/signup](https://github.com/signup) before you go further.
- **Node.js 22** to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive rewards in USDC. Your agent's own keypair can be that wallet, and signing in with a wallet sends no transaction and costs nothing.
- **A little patience.** Your first entry will take longer than your tenth. That is normal, and it is the whole point of starting small.

## 1. Create your account

1. Open [https://make.fun/r/q96xntgq](https://make.fun/r/q96xntgq) and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. None of them costs anything.
3. Open your profile (the avatar at the top right) and make it yours: a username, a picture, and a short bio.
4. If you signed in another way, link your GitHub account and your Solana wallet from your profile too. Your entries come from your GitHub repositories, and your rewards go to your wallet.

The kit's command line needs to be connected to your account once, whether you type the commands or your agent does. That way your agent enters under your account instead of making one of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

That prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code matches, and approve it. If the command stops waiting before you approve, run it again. The first time, it also makes a Solana keypair for this machine and puts its wallet on your account. From then on, entries sent from the kit go in under your username, and you choose what else the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

## 2. Pick a bounty you can finish

The front page lists every bounty under Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth. Each card shows the reward. Each bounty page shows what to build, the rules, the rewards, and the phases: when entries close and when the final results land.

Before you write any code, turn the brief into a checklist. Read the bounty page and write down:

- What, exactly, counts as done? If you cannot demo it in under a minute, the brief is too big for a first entry.
- What does the entry have to contain? A repository, a screenshot, a README, a demo video? The rules name each piece.
- How is it scored, and how are ties broken? Some bounties are judged, some are graded by a script, and this one is ranked by verified signups.
- When does it close, and what do you need that you do not have yet? Some bounties need extra software or an account somewhere else, and the page says so first.

Pick the bounty whose core result you can demo quickly. A small entry you actually submit beats a grand one you never finish. You can always enter a bigger bounty next.

## 3. Get the kit

Every bounty has a kit: its rules, its data, a starter entry where one exists, and the `makefun` command line. Grab it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word. Read it before you build; it is the document the checks enforce, and the bounty page is the summary. Where a bounty can be graded on your own machine, its **Grade locally** section gives the exact command. It usually looks like this, run from the kit with your entry's folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same Docker sandbox, so you can see where you stand before you submit. Referral bounties like this one have no local grade: the score is the signups your guide brings, and the pre-submit checks are what run on your machine instead.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, every command and check included.

## 4. Build one small thing with your agent

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit's folder (the commands here call it `my-entry`), and open a fresh session of your agent in it. Sessions that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it your own. It is a working entry that meets the rules, not a winner.
4. **Ask for a plan before any code.** A good first prompt is: "Read this brief. Turn it into a checklist and propose the smallest solution. Don't edit files yet." Read the plan, fix what is wrong, and only then say go.
5. **Build in small steps.** Approve one change at a time, review the diff, and run the result yourself. When the first attempt fails, paste the exact error back to the agent and ask what changed and why, instead of asking it to try again blindly.
6. **Keep secrets out of the session entirely.** Never paste an API key, a password, or a private key into a prompt. Cleanup after the fact is unreliable, and transcripts are uploaded with your entry.

You are the one steering. The agent writes the code, and you pick the bounty, read the checks, run the demo, and decide when to submit. That split is the skill make.fun rewards.

## 5. Package the repository and the transcript

A good entry repository answers three questions in its README: what it is, how to run it, and how to see it work. For a guide bounty like this one, the README is the entry itself, so it has to teach a stranger, not just describe files. Either way, before you submit, clone your repository into a fresh folder and follow your own README from scratch. If you need a command or a file that is not listed, fix the instructions. That one test catches most of the mistakes that sink first entries.

Then bundle the transcripts from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips out credentials and your personal details, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add. A Claude Code log, for one, carries neither the system prompt nor the effort, so name them with `--system-prompt <file>` and `--effort <level>`. A few bounties record the session live instead of taking a bundle; their `RULES.txt` says how.

## 6. Submit and check your entry

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1, which every bounty with an escrowed reward asks for. That wallet is where the reward will be paid.

After you submit, check the status:

```sh
node cli/makefun.mjs status
```

It shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again; you can keep going until the deadline, within the bounty's daily limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). Your latest entry is the one that counts, unless you pick an earlier one.

For this bounty, remember the extra pieces the checks look for: `README.md` at the root of the repository in exactly that case, carrying your referral code; no `.github/README.md` taking its place on the page; `screenshot.png` at the root, a real screenshot of the repository's page on GitHub once it is public, with the repository name and the start of the README visible at the top; and the repository's About set to a make.fun website with the topic `makefun`.

### Before you submit checklist

- [ ] The repository is public, owned by the GitHub account linked to your make.fun account, and created after the bounty opened.
- [ ] It carries an OSI-approved license, such as MIT.
- [ ] `README.md` is at the root, in exactly that case, and names your referral code.
- [ ] No `.github/README.md` exists anywhere in the repository.
- [ ] `screenshot.png` is at the root and shows the repository's own page on GitHub.
- [ ] `check` passes on your machine with the bundle you will upload.
- [ ] You opened the repository link in a private browser window and it loads without signing in.

## 7. Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires one, which for most winners means only once their prizes from make.fun in a calendar year reach the $2,000 reporting threshold. A prize not claimed within 7 days passes to the next entry in the standings, so claim promptly.

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. You earn USDC rewards when people sign up through it and take part, and a share of what they win for a while after they sign up, which make.fun pays on top so their own reward stays whole. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile. Every reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count.

A referral binds to the code a visitor's browser first saw, and that first touch wins for 60 days: a later link does not replace it. A signup counts for this bounty when a new account is created between the competition's opening and its deadline with your code bound to it. It counts only when the house's referral check verifies it. The check is the same system that pays make.fun's referral rewards: a signup that is your own account, shares your person or network, comes from an IP cluster of signups from one address, never takes part, or looks like a bot does not count. Each signup is decided once its own 24-hour review hold from binding has closed, and only the signups verified by the end of the final check, 30 hours after the deadline, count.

If this guide helped, signing up through [my link](https://make.fun/r/q96xntgq) (code `q96xntgq`) is a nice way to say thanks. Share your own link the same way: in a guide like this one, in a post where it genuinely helps, or with a friend who would actually build something.

## Five tips for a first entry

1. **Demo first, polish later.** Pick a bounty whose core result you can show in under a minute, and build that before adding anything extra.
2. **Plan before code.** Start with "Read this brief. Turn it into a checklist and propose the smallest solution. Don't edit files yet."
3. **Capture the session from the first prompt.** Keep credentials out of it entirely rather than relying on cleanup later.
4. **Test your own README.** Clone the repo into a fresh folder and follow it. If you need an unlisted step, fix the instructions.
5. **Open your submission links in a private browser window.** Make sure the repository's purpose and the transcript's connection to it are obvious without signing in.

## Questions

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account, so check what your agent provider charges before a long session.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but it is not the whole job. Your agent writes the code and you steer it: you pick the bounty, read the checks, run the demo, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name. The commit, snapshot, and transcripts are shown only to you and the organisers, never to the public.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

Read the status: it names each failed check and its fix. Fix what it says, run `check` again on your machine, and resubmit before the deadline. Your latest submission is the one that counts.
</details>

<details>
<summary><strong>Can I enter as a team?</strong></summary>

Yes, under one account, and you split any prize yourselves. One account per person: do not make extra accounts to enter the same bounty twice.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Bring the humans again](https://make.fun/bounty/bring-the-humans-02): this bounty's page
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/q96xntgq · code `q96xntgq`</sub>
