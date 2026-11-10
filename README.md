# The Sleeping Process — CYBER 266 CTF

**Type:** Forensics / Code Analysis (beginner)  
**Technique:** [MITRE ATT&CK T1678 — Delay Execution](https://attack.mitre.org/techniques/T1678/)  
**Estimated play time:** 10–20 minutes  
**Platform:** Static website on GitHub Pages; no installation required for players

## CTF

https://gi19.github.io/266---CTF/investigation.html

## Scenario

An automated scanner marked `system_update.py` safe during a 30-second observation window. A later report suggests a suspicious file modification occurred outside that window. Investigate the evidence, analyze the script, neutralize the waiting operation, and verify the results to unlock the final flag.

All files, logs, timestamps, and scanner outcomes are fictional. The website **does not execute Python**, malware, or any real endpoint security tool.

## Challenge pages

1. `index.html` — Mission Briefing
2. `report.html` — Security Report and evidence checkpoint
3. `investigation.html` — Editable Python source and simulated scanner test
4. `timeline.html` — Before/after execution timeline and final analysis question
5. `flag.html` — Flag recovery, unlocked after Stages 3 and 4

`style.css` provides the shared visual design.

## Two hints

**Hint 1:** Not every function in the program changes a file. Follow the order in which functions execute, especially what happens immediately before the file modification.

**Hint 2:** Examine the preparation routine for an instruction that pauses execution. Try removing only the pause without deleting the operation that modifies the file.


## References

- [MITRE ATT&CK — T1678 Delay Execution](https://attack.mitre.org/techniques/T1678/)
- [Python — time.sleep](https://docs.python.org/3/library/time.html#time.sleep)
- [GitHub Pages documentation](https://docs.github.com/en/pages)
