# Football-Prediction
Predicting football outcomes whether Home-win, Draw or Away-win (1, X, 2).

# 📊 Columns Breakdown
## 🔑 Identifiers

Match_ID → unique Sofascore fixture ID (we’ll scrape this from the API).

Date → match date/time.

League → league/tournament name.

Home_team / Away_team → team names.

## 🏆 League Context

Home_team_league_position

Away_team_league_position
➡️ Scraped from Sofascore’s standings endpoint.

## 📈 Form

Home_team_form (last 5 games, W/D/L or points).

Away_team_form
➡️ Can be built by scraping recent results → convert to a numeric score (e.g. W=3, D=1, L=0).

## 💰 Odds

Home_team_odds

Draw_odds

Away_team_odds
➡️ Sofascore often provides bookmaker odds (if missing, we’ll find an odds API).

## ⚔️ Head-to-Head

H2H_home_wins

H2H_draws

H2H_away_wins
➡️ Sofascore has H2H history per fixture (scrapable).

## ⚽ Goals & Stats

Home_team_goal_difference

Away_team_goal_difference
➡️ From league table (GF - GA).

Home_team_goals_for / Away_team_goals_for

Home_team_goals_conceded / Away_team_goals_conceded
➡️ Also from league table stats.

## 🚑 Injuries

No_of_key_injuries_home

No_of_key_injuries_away
➡️ Sofascore shows injuries/suspensions per team (scrapable). We can simplify to just counts first.

## 📊 Advanced Metrics

xG_home / xG_away
➡️ Trickier — not always available in Sofascore. Some matches/leagues have xG, but coverage is inconsistent. If missing, we can drop or replace with another performance metric.

## 🏁 Target

Match_result (Home, Draw, Away)
➡️ Scraped after match finishes — but only used for training labels, never prediction inputs.

## ⚡ Roadmap with These Features

Step 1: Collect basic fixture data (Match_ID, Date, League, Teams).

Step 2: Add standings (positions, GF, GA, GD).

Step 3: Add form (past 5 matches per team).

Step 4: Add odds & H2H.

Step 5: Add injuries (counts).

Step 6: Add xG if available.

Step 7: Collect results for training labels.