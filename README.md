# The viral agent

Five Claude skills that take you from "what should I make?" to a finished faceless reel. Free, and open source under the MIT licence. Nothing gets posted until you post it.

| Skill | What it does |
|---|---|
| `/viral-find` | Finds the reels beating their own account's normal in your niche, and works out why. |
| `/viral-script` | Writes three hooks and a script that sounds like you, with a picture for every line. |
| `/viral-animate` | Turns the script into a 3D animated video, written in code, with no camera or animator. |
| `/viral-voice` | Adds the voice, word-timed captions and sound effects, and exports the finished video. |
| `/viral-check` | Checks the reel before you post it, and rewrites the hook if it's weak. |

## Install

You need Claude Code. Paste this into it:

```
https://github.com/hadi-a-azeez/viral-agent

Install these skills, run their setup, then make me a test reel to confirm they work.
```

Or do it by hand:

```bash
git clone https://github.com/hadi-a-azeez/viral-agent.git
mkdir -p ~/.claude/skills
cp -r viral-agent/skills/viral-* ~/.claude/skills/
bash ~/.claude/skills/viral-animate/setup.sh
bash ~/.claude/skills/viral-voice/setup.sh
```

Or as a plugin, in Claude Code:

```
/plugin marketplace add hadi-a-azeez/viral-agent
/plugin install viral-agent@viral-agent
```

Then run the two setup scripts from the plugin's `skills/viral-animate` and `skills/viral-voice` folders, or ask Claude to.

The setup needs [Node.js](https://nodejs.org) 18 or newer, [ffmpeg](https://ffmpeg.org) and Python 3. It tells you if any of them is missing. It reuses Google Chrome if you have it, otherwise it downloads Chromium once.

Then spend five minutes on `templates/profile.md`. Copy it to `~/.claude/viral/profile.md` and paste in three things you've really said. Skip it and your scripts will sound like everyone else's.

## Use it

Just ask, in your own words:

```
Find what's working in the personal finance niche. Start with these accounts: ...
```

Each skill hands over to the next. You can also start in the middle: bring your own idea to `/viral-script`, or any finished reel to `/viral-check`.

## What it costs

| Part | Cost |
|---|---|
| These five skills | Free |
| Rendering, captions, sound effects | Free, it runs on your computer |
| Free voice (Malayalam, English, Hindi, Tamil and more) | Free |
| Your own voice | Free, and usually the best option |
| Claude | You need a Claude plan that includes Claude Code |
| Automatic reel finding | Optional. Apify charges about $0.0026 per reel. Screenshots are the free route |
| ElevenLabs voice | Optional. Their pricing applies |

## What it won't do

- **It can't promise views.** Nobody can. Even accounts with huge hits have plenty of quiet reels. It helps you make better videos and it catches common mistakes. The rest is your idea, your consistency and some luck.
- **It won't post for you.** You watch the reel and you decide.
- **It doesn't draw people or animals.** It draws objects, places, light and type. Plenty of stories work well this way.
- **It won't copy other creators.** It borrows the structure of what works, and your script uses your words.

The free voice runs on Microsoft's Edge read-aloud service through the open-source `edge-tts` tool. It isn't an official API, so it could change. Check the terms before using it for client or commercial work.

## What's been tested

- **Tested end to end on a Mac with Apple Silicon:** a clean install with and without Google Chrome, finding outliers on real Instagram data, scripts, rendering, the free Malayalam voice, caption timing on a real recording, the sound mix and the check.
- **Not tested on Windows or Linux yet.** It should mostly work, but expect some rough edges.
- **ElevenLabs and `APIFY_TOKEN`:** only tried against a stand-in server, so they may need a small fix with a real key. If you hit one, Claude can usually sort it out for you.

## Licence

MIT. See [LICENSE](LICENSE).
