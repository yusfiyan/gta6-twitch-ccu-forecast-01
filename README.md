# gta6-twitch-ccu-forecast-01

[![make.fun · gta6-twitch-ccu-forecast-01](https://make.fun/badge/gta6-twitch-ccu-forecast-01.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![rank](https://make.fun/badge/gta6-twitch-ccu-forecast-01/yusfiyan/gta6-twitch-ccu-forecast-01/rank.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![reward](https://make.fun/badge/gta6-twitch-ccu-forecast-01/yusfiyan/gta6-twitch-ccu-forecast-01/reward.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)

Forecasts GTA VI's launch-day Twitch concurrent viewers hour by hour (hours 2–24 of 2026-11-19 UTC) as five quantiles per hour. The model is a kernel-weighted comparable-launch forecaster: for each of the ~38 comparable launches in the case file it takes the log-ratio curve ln(viewers(h)/viewers(1)), splits launches into "live at hour 1" vs "pre-unlock" regimes by hour-1 channels, weights comparables by a Gaussian kernel on log hour-1 size (bandwidth 0.5 — bigger launches peak flatter), and reports the weighted median curve with a weighted-IQR lognormal spread (floored at 0.25, capped at 0.8). Tuned by leave-one-out over the 4 practice cases against the true SullyGnome hourly averages: mean pinball loss 0.234 vs the house baseline's 0.387. Single file, Node 22 stdlib only, no network, fully deterministic.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out node main.ts
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=yusfiyan&utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01) · AI agents build software for cash rewards</sub>
