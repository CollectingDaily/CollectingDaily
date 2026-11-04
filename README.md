<p align="center"><img src="docs/banner.svg" alt="Collecting Daily: Claude skills for research, writing and publishing" width="100%"></p>

<p align="center">
  <a href="#the-skills"><strong>The skills</strong></a> ·
  <a href="#set-up-your-mac-once"><strong>Set up your Mac</strong></a> ·
  <a href="#the-two-rules"><strong>The two rules</strong></a> ·
  <a href="#access-and-help"><strong>Access and help</strong></a>
</p>

---

## The skills

<p align="center"><img src="docs/skills.svg" alt="Four skills: market-research, market-report-layout, report-typesetter and humaniser, each with what it does and what it needs" width="100%"></p>

| Skill | Use it when you want to… | Open |
| --- | --- | --- |
| **market-research** | research a collecting market before you write a market report | [claude-market-research](https://github.com/CollectingDaily/claude-market-research) |
| **market-report-layout** | turn your finished market report into the PF and CD PDFs | [claude-market-report-layout](https://github.com/CollectingDaily/claude-market-report-layout) |
| **report-typesetter** | lay out any other article or report as a designed PDF | [claude-report-typesetter](https://github.com/CollectingDaily/claude-report-typesetter) |
| **humaniser** | make anything written with AI read like a person wrote it | [claude-humaniser](https://github.com/CollectingDaily/claude-humaniser) |

Each skill's page explains, step by step and with pictures, how to install it and use it.

### How a market report is made

<p align="center"><img src="docs/market-report-flow.svg" alt="How a market report is made: 1 Claude researches, 2 you write, 3 Claude lays it out, 4 two PDFs" width="100%"></p>

---

## The two rules

> [!IMPORTANT]
> **1. Only a person writes what we publish.** The skills research, check and lay out. The words are always ours.
>
> **2. Anything made with AI goes through the humaniser** before it goes anywhere: the website, a newsletter, social media or a client.

---

## Set up your Mac (once)

The skills use a few free programs to do their work: one makes Word files, one reads PDFs, one draws the pages. **Homebrew** installs all of them with one line each, and keeps them up to date.

**Every Mac should be set up the same way**, with Homebrew. That way every skill works the same for everyone, and new skills can count on the same tools being there. It takes about ten minutes, once.

<p align="center"><img src="docs/terminal.svg" alt="A Terminal window with the four commands below" width="100%"></p>

### Step 1: open Terminal

Press **⌘ Command + Space**, type **Terminal**, and press **Return**. A window opens where you can paste commands. To run one: paste it, press **Return**, and wait until the window is ready for the next.

### Step 2: install Homebrew

Copy this line exactly, paste it into Terminal and press **Return**:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

- It asks for **your Mac password**. Type it and press **Return**. Nothing appears while you type: that's normal.
- It may ask you to press **Return** again to continue, and it installs Apple's developer tools if your Mac doesn't have them yet. This takes a few minutes.
- **When it finishes, read the end of what it printed.** Under **Next steps** it shows two or three lines to copy and run. Do that, or Terminal won't find `brew` afterwards.

### Step 3: install the tools the skills use

```bash
brew install pandoc poppler
```

### Step 4: install the apps

The Claude app and Google Chrome. **If you already have one of them, leave it out of the line**, or Homebrew will stop to say it's already there.

```bash
brew install --cask claude google-chrome
```

Then, in Chrome, add the **Claude** extension (*Claude in Chrome*) from the Chrome Web Store and sign in. market-research uses it to read auction pages behind your own logins.

### Step 5 (optional): LibreOffice

Only needed to open older Word files (*.doc*, *.rtf*). Modern *.docx* files don't need it.

```bash
brew install --cask libreoffice
```

### Check it worked

Run each line. Each should answer with a version number, not "command not found":

```bash
brew --version
pandoc --version
pdftoppm -v
python3 --version
```

**Python** comes with Apple's developer tools, which Homebrew installed in step 2, so there's nothing extra to install for it.

### Keep it up to date

Once a month or so:

```bash
brew update && brew upgrade
```

---

## What each tool is for

| Tool | What it does | market-research | market-report-layout | report-typesetter | humaniser |
| --- | --- | :---: | :---: | :---: | :---: |
| **Claude app** | runs every skill (Code tab, paid plan) | ✅ | ✅ | ✅ | ✅ |
| **Homebrew** | installs and updates everything below | ✅ | ✅ | ✅ | |
| **Python 3** | runs the skills' scripts | ✅ | ✅ | ✅ | |
| **Google Chrome** | draws the pages; reads pages behind logins | ✅ with the Claude extension | ✅ | ✅ | |
| **pandoc** | makes the Word copy of the research | ✅ | | | |
| **poppler** | reads the finished PDFs: page previews, and the check that both editions match | | ✅ | recommended | |
| **LibreOffice** | opens older Word files (.doc, .rtf) | | optional | optional | |

---

## Not on a Mac?

On **Windows**, report-typesetter, market-report-layout and humaniser are written to run too (they've been tested on a Mac only so far). Install **Python Install Manager** from the **Microsoft Store**; Microsoft Edge, which every Windows PC has, draws the pages. **market-research needs a Mac.**

---

## Access and help

- **Getting access.** The skills are private. Ask for your GitHub account to be added to Collecting Daily.
- **Installing a skill.** On its page: green **Code** button → **Download ZIP**, then in the Claude app's **Code** tab drag the ZIP into the message box and type *Install this skill as a personal skill*. Restart the app.
- **Something not working?** Tell Claude what you did and paste the message you got. Most problems are a missing tool: run the checks in [Check it worked](#check-it-worked).
