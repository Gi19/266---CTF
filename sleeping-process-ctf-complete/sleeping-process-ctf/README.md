# The Sleeping Process — CYBER 266 CTF

**Type:** Forensics / Code Analysis (beginner)  
**Technique:** [MITRE ATT&CK T1678 — Delay Execution](https://attack.mitre.org/techniques/T1678/)  
**Estimated play time:** 10–20 minutes  
**Platform:** Static website on GitHub Pages; no installation required for players

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

## Run locally

Open `index.html` in a browser, then click **Start Investigation**. All stages work without Docker, Python, or a web server. Browser `sessionStorage` tracks stage completion within the current tab/session; reopening the challenge in a different tab or session may reset progress.

## Publish on GitHub Pages

1. Create a repository such as `sleeping-process-ctf`.
2. Upload all five HTML files, `style.css`, and this `README.md` to the repository root.
3. In **Settings → Pages**, select **Deploy from a branch**, branch `main`, directory `/(root)`.
4. Your website will normally be at `https://YOUR-USERNAME.github.io/sleeping-process-ctf/`.

Replace `YOUR-USERNAME` with your actual GitHub username.

## Developer / instructor notes

- The intended solution is a minimal source edit that eliminates the execution delay while preserving the file modification. Scanner results are simulated in the browser.
- Stage 4 explains why the modified program is detected during the scanner's 30-second observation period and the original one is not.
- The exact simulated file-modification time in the original scenario is **14:33:39**; the **14:34:07** event is the time a separate report was received.
- The flag is protected only by client-side game logic and is therefore inspectable in source code. This is sufficient for a casual educational demonstration, **not** a tamper-resistant CTF. For stronger protection use server-side validation on an appropriate hosting platform.
- Keep the separate full walkthrough/solution guide out of the public player repository until after the class CTF event if you want to preserve the puzzle.

## References

- [MITRE ATT&CK — T1678 Delay Execution](https://attack.mitre.org/techniques/T1678/)
- [Python — time.sleep](https://docs.python.org/3/library/time.html#time.sleep)
- [GitHub Pages documentation](https://docs.github.com/en/pages)
