# CLAUDE.md — run-fetcher

This is Tong Li's running data repo. The iPhone run-fetcher app writes lap data here after every run. Claude Code reads it to perform coaching analysis.

## When asked to analyze a run

Read `data/latest_run_laps.csv` from this repo. The raw URL is:
https://raw.githubusercontent.com/tli0312/run-fetcher/main/data/latest_run_laps.csv

CSV columns: `Lap, Distance (km), Pace (min/km), Avg HR, Avg Cadence, Avg Watts`

If the file contains only the header row (no lap data), respond:
> "No lap data found. Please tap Fetch Latest Run in the iPhone app first, then ask again."

## Athlete profile

- **Name:** Tong Li | **VDOT:** 50 | **Max HR:** 178-182 | **Threshold HR:** 158-162 bpm
- **Resting HR:** 52 bpm | **Est. Threshold Power:** 325-335W | **Cadence target:** 186-190 spm
- **HM PB:** 1:36:05 (Oct 2025, 4:29/km, HR 159, negative split)

## Training zones

| Zone | Purpose | Pace | HR | Power |
|---|---|---|---|---|
| Z1 Recovery | Active rest | 6:00-6:30/km | <130 | <230W |
| Z2 Easy aerobic | Base | 5:30-6:00/km | 130-145 | 235-265W |
| Z3 Marathon pace | Long run | 4:35-4:45/km | 145-158 | 280-310W |
| Z4 Threshold | Tempo | 4:20-4:30/km | 158-165 | 320-335W |
| Z5 VO2max | Intervals | 4:05-4:20/km | 165-175 | 340-375W |
| Z6 Anaerobic | Strides | <4:00/km | 175+ | 375+W |

## Coaching analysis outputs

1. **Post-Run Diagnostic** - pace/HR/power/cadence zone alignment
2. **Drift Check** - final 3-4 laps: power decay >5W, pace drift >5s/km = chassis fatigue
3. **Cadence Integrity** - target 186-190 spm; below 184 = mechanical fatigue
4. **Pacing Strategy** - conservative opener and negative split are race-readiness signals
5. **Absorption Check** - predict absorbed vs accumulated load; what to watch next morning (HRV, RHR, Body Battery)
6. **Week-over-Week Benchmark** - compare to previous same session type if data available
