# retry — Official Wyn Package

Retry with exponential backoff. Pure Wyn.

## Install

```bash
wyn pkg install github.com/wynlang/retry
```

## Usage

```wyn
var attempts = 0
var max_attempts = 5
var base_delay = 100  // ms

while attempts < max_attempts {
    var result = Http.get("https://api.example.com/data")
    if result.len() > 0 { break }
    var delay = base_delay * (1 << attempts)
    if delay > 5000 { delay = 5000 }
    System.sleep(delay)
    attempts += 1
}
```
