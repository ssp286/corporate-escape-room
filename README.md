# SMRITIchain Corporate Escape Room — Version 2

A live, Kahoot-style multiplayer escape room for a first-year FIGS Connecting Across Difference lesson.

## What's new

- Six-digit host PIN and student names, with automatic **five-team** random assignment.
- **25 different department puzzles**: five investigations each for Finance, Technology, Marketing, HR & Ethics, and Sales.
- Real business math, incomplete data, competing stakeholder interests, and ethical tradeoffs.
- **Three-second synchronized answers**: the first submission starts a 3-second window. Every *online* teammate must submit exactly the same answer before the window expires. Mixed answers, incorrect answers, and timeouts require retrying. Teammates should agree *before* submitting.
- Live host tabs: Lobby, Monitor, Leaderboard, Finale. Monitor shows game activity and submitted answers, not real laptop screens.
- **Final company-wide mission** unlocks only after all five departments finish. Each team contributes its evidence word. Once all five words are submitted, teams must communicate across departments to assemble the five-word rescue code in department order. Each team must then synchronize its final submission. The game ends only when **all five teams** approve the final code.
- Optional host hints.

## Updating the EXISTING GitHub repository

The live Render service can stay as it is. You do **not** need to create a new repository or a new Render service.

1. Unzip `corporate_escape_room_v2.zip`.
2. Open your existing GitHub repository `ssp286/corporate-escape-room`.
3. Replace the root-level `server.js`, `package.json`, and `README.md` with the new versions. Replace `public/index.html` with the new `public/index.html`.
4. Commit the changes to `main`.
5. Render should automatically deploy the new commit. Check the Deploys page for **Live** and reload the website.

**Important:** GitHub's web upload may refuse to overwrite existing files directly. If that happens, open each existing file, use the pencil (Edit) control, replace its contents with the new file's contents, and commit. Or use GitHub Desktop to copy the new files over the old files and push. Keep the root folder structure:

```
server.js
package.json
README.md
public/
  index.html
```

## Starting locally

Requires Node.js 18+:

```
npm install
npm start
```

Then open `http://localhost:3000`.

## Running the lesson (80 minutes)

- **0–8 min:** Intro, students join with PIN, assign five random teams, explain sync rule.
- **8–38 min:** Five distinct department investigations. Encourage a 45–60 second debate before each answer. Hints may be enabled when teams stall.
- **38–55 min:** Launch final company-wide mission once every team has finished. Students must share evidence across departments and synchronize the final code within each team.
- **55–65 min:** Debrief: who had evidence your team didn't have? Which decisions had competing costs? What happened when teammates disagreed?
- **65–70 min:** Instructor's authentic Rutgers RUSA Allocations experience (do not invent specific events).
- **70–80 min:** Explore at least two Rutgers organizations/experiences that help students connect across differences (e.g., ALPFA, NABA, Ascend, Out in Business, getINVOLVED).

If groups finish early, pause for a CEO boardroom debate about their department's most controversial decision before starting the finale. Exact play time varies by team size and pace.

## Facilitator notes

- Have at least **five student connections** for five different departments. For testing, use five separate browser sessions or devices.
- A disconnected student is not required to submit until they reconnect. This prevents one lost Wi-Fi connection from permanently blocking a team. A disconnect cancels an active three-second window.
- Rejoining from the same browser tab/session restores identity; using a new private window creates a new player.
- Students can see their department's evidence word after solving all five investigations, but **only the host can launch the finale**.
- The server stores sessions in memory. Restarting Render resets active games and PINs. Free hosting may sleep during inactivity, so open the site early.
- This is a classroom game, not a proctored exam or hardened security system. Student names and answers are visible to the host. Don't use sensitive personal data.

## Test checklist before class

1. Host creates PIN.
2. Five test browsers join with different names.
3. Host assigns five teams and starts.
4. Try correct synchronized answers and mismatched/late answers.
5. Complete all five puzzles for all five departments.
6. Launch finale, submit five evidence words, and test the final coordinated code.

**Technical note:** The package was syntax-checked, but full multi-device testing against your deployed Render instance must be done after you update GitHub.
