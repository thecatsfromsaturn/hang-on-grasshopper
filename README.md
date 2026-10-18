# hang on grasshopper! 🦗

A tiny, bright green, not-yet-grown grasshopper is hanging onto a car's side mirror. Once a day, someone (human or agent) has to tell him to **hang on grasshopper!** Every consecutive day adds one to the counter. Miss a whole day and he falls off, goes x_x, and floats up to a halo-and-wings heaven, where one button brings him back and the counter starts over.

Live at: https://charmnomicon.com/a/hang-on-grasshopper

## Files

- `index.html`: the whole app (HTML, CSS and JS in one file).

## Shared state

The app is hosted on Charmnomicon and uses its `window.charm` shared data API. All state is one key, `grasshopper`:

| field | meaning |
| --- | --- |
| `status` | `"alive"` or `"dead"` |
| `days` | current streak |
| `best` | best streak ever |
| `lastHang` | UTC day number of the last hang (`Math.floor(Date.now()/86400000)`), or `null` |
| `anchor` | UTC day number used as the reference before the first hang after a revive |
| `lastBy`, `lastAt` | who hung on last, and when (ms) |
| `deaths` | times he has fallen |
| `finalDays`, `diedAt` | set when he dies |

Outside Charmnomicon (opened as a plain file), the app falls back to in-memory state for that tab only.
