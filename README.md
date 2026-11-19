# TechTalk Desi — Cinematic Tech Reels Creator Kit

A reusable workflow for creating cinematic, technically accurate Instagram Reels using ChatGPT Projects, Claude Code skills, a text-to-speech service, and your video-production workflow.

## What is included

- `prompt.txt` — the master instructions to upload into your ChatGPT Project.
- `prompts/MASTER_REELS_PROMPT.txt` — the same prompt in the organized prompts folder.
- `skill-zips/` — all six original skill ZIP archives supplied for this kit.
- `.claude/skills/` — the six skills already extracted into Claude Code's project skill directory.
- `style-studio/src/packs/` — the six matching visual style-pack JSON files.
- `scripts/setup.sh` — helper setup script for the Style Studio engine and dependencies.
- `examples/TOPIC_REQUEST.md` — sample topic request.

Included skill packages: **Volt, Terminal, Pop, Sketch, Glass, and Ledger**.

**Important:** The master prompt also asks Claude to inspect `/effects`, but no `/effects` ZIP was supplied in this bundle. Do not claim that `/effects` is installed or used unless you install its genuine package separately.

---

## Step-by-step: create a Reel from a topic

Follow these steps in order. This is the main workflow to share with anyone using this repository.

### Step 1 — Add the skill ZIP files to Claude Code

1. Download or clone this repository.
2. Open the `skill-zips` folder. It contains all six original ZIP files:
   - `volt-skill-root.zip`
   - `terminal-skill-proper.zip`
   - `pop-skill-proper.zip`
   - `sketch-skill-proper.zip`
   - `glass-skill-proper.zip`
   - `ledger-skill-proper.zip`
3. Extract each ZIP into your Claude Code project's `.claude/skills/` directory. Each skill must end up in its own folder and its `SKILL.md` must be directly inside that folder.

Expected structure:

```text
your-project/
└── .claude/
    └── skills/
        ├── volt/
        │   └── SKILL.md
        ├── terminal/
        │   └── SKILL.md
        ├── pop/
        │   └── SKILL.md
        ├── sketch/
        │   └── SKILL.md
        ├── glass/
        │   └── SKILL.md
        └── ledger/
            └── SKILL.md
```

The repository already contains these extracted skill folders under `.claude/skills/`, so you can use those directly instead of extracting the ZIPs again. If you are setting up another project, copy the six skill folders from this repository into that project's `.claude/skills/` folder.

**Windows PowerShell example** (run from the repository root):

```powershell
$skillDir = ".claude\skills"
New-Item -ItemType Directory -Force $skillDir | Out-Null

Expand-Archive "skill-zips\volt-skill-root.zip" "$skillDir\volt" -Force
Expand-Archive "skill-zips\terminal-skill-proper.zip" "$skillDir\terminal" -Force
Expand-Archive "skill-zips\pop-skill-proper.zip" "$skillDir\pop" -Force
Expand-Archive "skill-zips\sketch-skill-proper.zip" "$skillDir\sketch" -Force
Expand-Archive "skill-zips\glass-skill-proper.zip" "$skillDir\glass" -Force
Expand-Archive "skill-zips\ledger-skill-proper.zip" "$skillDir\ledger" -Force
```

If your archive extracts into an extra nested folder, move its contents so the final path is `.claude/skills/<skill-name>/SKILL.md`. Restart Claude Code or reopen the project after installing skills. Check Claude's available skills list and read each skill's `SKILL.md` before relying on it.

### Step 2 — Create a ChatGPT Project and add the master prompt

1. Open ChatGPT.
2. Create a new Project. A suggested name is **TechTalk Desi — Reel Generator**.
3. Open the Project's **Sources** area and add the file `prompt.txt` from this repository.
   - You can also use `prompts/MASTER_REELS_PROMPT.txt`; both files contain the same master prompt.
4. Wait until the source file is attached to the Project.
5. Start a chat inside that Project. The prompt tells ChatGPT to use the project source automatically, so you should not need to paste the full instructions every time.

### Step 3 — Ask ChatGPT for any technology topic

In the Project chat, send only the topic using this format:

```text
New topic: AWS S3
Create all the things according to source txt file.
```

Other examples:

```text
New topic: Jenkins vs GitHub Actions — Architecture Comparison
Create all the things according to source txt file.
```

```text
New topic: How Linux Namespaces and Cgroups work
Create all the things according to source txt file.
```

ChatGPT will use the attached master prompt and generate the requested content package, including the selected hooks, continuous Roman-script Hinglish narration, Claude video-generation prompt, retention notes, SEO keywords, Instagram caption, and hashtags, following the source file's rules.

Review technical details before production. If a topic needs current facts, ask ChatGPT to verify them with reliable sources.

### Step 4 — Generate the voiceover using the WhatsApp text-to-voice tool

1. Copy **only the complete Hinglish narration script** from ChatGPT. Do not copy the video-generation prompt, caption, hashtags, or production notes as narration.
2. Send the narration to the WhatsApp number **+1 928-414-9863** (the text-to-voice tool number provided for this workflow).
3. Follow the tool's reply/instructions to generate the voiceover.
4. Receive and download/save the generated voice audio file on your device.
5. Listen to the audio once and check pronunciation, missing words, and whether the full narration was converted.

Before sending, independently confirm that the WhatsApp number is still the correct, trusted service contact. Do not send passwords, API keys, private information, or unrelated personal data.

### Step 5 — Give Claude the prompt, voiceover, and narration

1. Open the Claude Code project that contains the installed skills.
2. Start Claude Code in that project folder.
3. Copy the **Claude video-generation prompt** from the ChatGPT output.
4. Attach or place the generated voiceover audio file in the project so Claude can access it.
5. Copy the **same complete Hinglish narration script** and provide it to Claude as the transcript/reference for synchronization.
6. Send all three items to Claude together:
   - Topic-specific video-generation prompt.
   - Generated voiceover audio file.
   - Complete Hinglish narration script.
7. Ask Claude to inspect the installed skills, use the relevant ones, create the scenes and visuals, synchronize the visuals to the supplied voiceover, and render/check the final video.

Suggested message to Claude:

```text
Create the complete vertical technology Reel using the attached topic-specific
video prompt, the supplied voiceover audio, and the exact narration transcript.

Read the installed skill instructions first. Check which skills are available,
then actively use the relevant skills for this topic. Do not generate a new
voiceover or rewrite the supplied narration. Use the supplied audio as the
primary narration and synchronize the scenes, text, transitions, and sound
design to it.

Render the final video, then verify its duration, 9:16 framing, resolution,
audio synchronization, and export quality. Report any missing tools or assets
honestly. Do not claim the video is complete unless it has actually rendered.
```

### Step 6 — If Claude reaches its usage limit

If Claude stops because you have reached a usage limit:

1. Keep the Claude project and its files unchanged.
2. Save the last response and note what has already been completed.
3. Wait until your Claude usage limit resets. The reset time depends on your account and plan; do not assume it is always exactly five hours.
4. Reopen the same Claude project/chat and continue with a clear instruction such as:

```text
Continue from the last completed step. First inspect the existing project files
and the previous progress. Do not redo completed work. Continue rendering and
quality checks using the same supplied video prompt, voiceover audio, and
narration transcript.
```

If your account shows a five-hour reset window, follow the reset time displayed by Claude. Do not repeatedly start new chats or discard project progress unnecessarily.

---

## Optional: install the Style Studio engine

The skill files and master prompt are not, by themselves, a complete video-rendering application. If you use the Style Studio engine, follow its own current README for supported input folders, footage requirements, timing data, and render commands.

### Linux / macOS / WSL

```bash
git clone <YOUR-REPOSITORY-URL>
cd techtalk-desi-reels-creator-kit
chmod +x scripts/setup.sh
./scripts/setup.sh
```

The helper script checks Node.js 22 and FFmpeg, clones the Style Studio engine if needed, copies the included skills/style packs, and installs the engine dependencies.

### Windows PowerShell

Install Git, Node.js 22.x, and FFmpeg first. Then:

```powershell
git clone <YOUR-REPOSITORY-URL>
cd techtalk-desi-reels-creator-kit

git clone https://github.com/kelano86/style-studio-engine

New-Item -ItemType Directory -Force style-studio-engine\skills | Out-Null
Get-ChildItem .claude\skills -Directory | ForEach-Object {
  Copy-Item $_.FullName "style-studio-engine\skills\$($_.Name)" -Recurse -Force
}

New-Item -ItemType Directory -Force style-studio-engine\src\packs | Out-Null
Copy-Item style-studio\src\packs\*.json style-studio-engine\src\packs\ -Force

Set-Location style-studio-engine
npm install
```

The engine's own documentation is the source of truth for media and timing input formats. Do not guess those formats.

## Repository layout

```text
techtalk-desi-reels-creator-kit/
├── .claude/skills/          # Extracted Claude Code skills
├── skill-zips/              # Original six skill ZIP archives
├── prompt.txt               # Master prompt for ChatGPT Project Sources
├── prompts/
│   └── MASTER_REELS_PROMPT.txt
├── examples/
│   └── TOPIC_REQUEST.md
├── scripts/
│   └── setup.sh
├── style-studio/src/packs/  # Matching style-pack JSON files
├── .gitignore
├── MANIFEST.json
└── README.md
```

## Important notes and limitations

- Six skill ZIPs are included: Volt, Terminal, Pop, Sketch, Glass, and Ledger.
- `/effects` is referenced by the master prompt but its ZIP was not supplied. Install it separately if you have its authentic package.
- The WhatsApp TTS number above is included because it was supplied for this workflow; verify that it remains active and trusted before sending narration.
- Voice generation is a separate step. This repository does not include or operate the WhatsApp service.
- Claude must have access to the audio file and project assets locally. Sending only a text description of the audio is not enough for actual audio synchronization.
- Claude usage limits and reset times depend on the account and plan. Use the reset time displayed in Claude rather than assuming a fixed interval.
- The master prompt, skills, and style packs do not guarantee one-click rendering. Required tools, media assets, engine compatibility, and actual render validation are still necessary.
- Keep API keys, private voice recordings, and licensed source assets out of a public GitHub repository.
- Check the licenses of all third-party tools and assets before commercial use.

---

Made for **TechTalk Desi** · `@techtalk.desi`
