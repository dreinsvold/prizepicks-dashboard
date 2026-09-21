# PrizePicks Group Tracker

Production dashboard for the 2026 NFL PrizePicks group tracker.

## Production architecture

- `index.html` — application/UI code. It loads the canonical season data at runtime and should change only when application design or logic changes.
- `data/prizepicks_2026.json` — canonical season dataset. Normal weekly/card publishing updates this file.
- Git history is the rollback/archive mechanism; separate weekly JSON copies are not required.
- GitHub Pages provides the permanent player-facing URL.

## Weekly production workflow

1. Submit the completed PrizePicks screenshot and picker mapping in the operations chat.
2. Normalize and evaluate the card.
3. Verify the proposed card results and cumulative standings.
4. After explicit approval, update `data/prizepicks_2026.json` on `main`.
5. Do not modify `index.html` for routine weekly data unless UI/logic itself changes.
6. Verify the permanent GitHub Pages URL on mobile.

## Governing result rules

- Records use W-L-P.
- Pushes count toward Picks Made and W-L-P.
- Hit Rate = Wins / (Wins + Losses); pushes are excluded from the denominator.
- Push Performance Score = 50.00 Neutral and is included in Avg Performance.
- Pushes are included in pick-type and prop-category sample counts.
- A Push breaks an active Win/Loss streak but is neither a Win nor Loss.
- Leaderboard: Hit Rate → Wins → Avg Performance; exact ties remain tied.
- Promo picks are displayed with their card but excluded from participant standings and Performance analytics.
