# SMRITIchain Corporate Escape Room

A real-time, Kahoot-style classroom game with a six-digit join PIN, player names, random teams, five collaborative puzzle rooms, host controls, a team-screen monitor, and a leaderboard.

## Quick start

Requires Node.js 18+ and internet access to install dependencies.

```bash
npm install
npm start
```

Open `http://localhost:3000` on the host computer.

**For students on separate laptops:** `localhost` only works on the computer running the server. Deploy this project to a Node.js hosting provider that supports WebSockets (e.g., Render or Railway) and share the resulting HTTPS URL with students. Alternatively, if everyone is on the same Wi-Fi and your computer's firewall allows it, students can visit `http://YOUR-LAN-IP:3000`. A campus network may block device-to-device connections; deployment is more reliable.

## How to play

1. On your host laptop, select **Create host lobby**.
2. Project the six-digit PIN and share the website URL.
3. Students open the same website, enter the PIN and their names.
4. Select a team count and click **Randomly assign teams**.
5. Click **Start escape room**.
6. Use **Team screen monitor** to see each team's in-game stage, progress, latest submitted answer, and attempts. This is **not** remote viewing of students' actual laptop screens.
7. Use **Leaderboard** to track progress. End the game from the host controls.

## Classroom timing (80 minutes)

- 3:50–4:00: Welcome, story, join lobby
- 4:00–4:10: Teams and rules
- 4:10–4:45: Escape room
- 4:45–4:55: Debrief (different perspectives and listening)
- 4:55–5:00: Instructor's authentic Rutgers Allocations story
- 5:00–5:10: Students explore at least two ways to connect across differences through Rutgers organizations/experiences

## Notes

- Games live in server memory. Restarting the server resets games and PINs.
- Host identity is saved in the host browser's session storage for reconnection; student identity is similarly saved.
- Intended for a supervised classroom, not as a hardened public service. Use a private classroom URL and don't collect sensitive information.
- Five puzzle answers are validated on the server. Each team shares progress across its members.
- The current five puzzles are deliberately beginner-friendly; you can modify the `puzzles` array in `server.js` to make them harder.
