# thai-skills

Agent skills for writing Thai prose that reads like a native Thai writer, not AI output.

Adapted from [chakrit/kien-thai](https://github.com/chakrit/kien-thai) by Chakrit Wichian (MIT).
All writing rules — the seven frames, person deixis, and the eight reference files — are the original author's work.

## Skills

| Skill | Use |
| --- | --- |
| `skills/thai` (was `kien-thai`) | Write, edit, review, or translate Thai prose in one pass |
| `skills/thai-loop-audit` (was `kode-thai`) | Audit-and-fix loop over existing Thai prose until a full pass comes back `CLEAN` |

## Install

Copy both folders into your agent's skills directory (e.g. `~/.agents/skills/` or `.claude/skills/`):

```sh
git clone https://github.com/windfall-digital/thai-skills
cp -r thai-skills/skills/* ~/.agents/skills/
```

Then ask for Thai prose (`thai` triggers on its own), or run `/thai-loop-audit <file>`.

## Changes from the original

- Renamed `kien-thai` → `thai`, `kode-thai` → `thai-loop-audit`.
- Removed the Thai-native model route (`scripts/thai-route.sh`, `scripts/thai-native-draft.py`) and the instructions pointing to it. Drafting is done by the agent itself.
- Removed references to the original repo's pytest harness and `CLAUDE.md`.
- When the register is known, the agent loads only that register's sections of `register.md`, `examples.md`, and `exemplars.md`.
- When the audit loop finds a pattern no rule covers, it reports it to the user instead of pointing to the original repo's iteration discipline.

## License

MIT. See [LICENSE](LICENSE); original copyright © Chakrit Wichian.
