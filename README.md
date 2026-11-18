Two-mode bot for make.fun BTC Race 24h (btc-race-24h-20261118-1444). One bot, two rule-based strategies, selected only from the bar timestamps the harness itself sends (first_close_ms in hello, or the first bar's "t"): DEV mode runs C2-RSI (early-recovery EMA pullback, all-in, TP 1.5%, SL 2%, Chandelier trail 2xATR, 480-bar time stop) and RACE mode runs ACCUM-A strict (I2c / #3c-flat entry, $250/tranche accumulation, TP 3%, SL, trail, 240-bar time stop). No wall clock, no network, no files outside the repo, deterministic.

Local grades (kit harness, exact fill math, 2 runs byte-identical each):
- DEV window (this bounty's frozen window, fell -2.80%): +$13.28, 1 trade (entry bar 345, exit bar 506 on TP), maxDD 0.64%. Gate PASS.
- Same DEV bars with a race-range first_close_ms: $0.00, 0 trades (mode switch verified: the C2-RSI trade does not fire).
- VOLATIL regime with race-range timestamps: ACCUM-A behaviour confirmed (multi-tranche fills, TP/SL/trail/time exits); trades starting in the scored half total +$18.56 vs the Python backtest's +$18.47 (0.5% fill-model difference).
