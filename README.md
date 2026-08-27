# habibi-boost-1 - ProxRipper SECOND 50k Booster

Second 50k proxy booster (50k-100k) from [ProxRipper](https://github.com/Mohammedcha/ProxRipper).

- **Source:** `https://raw.githubusercontent.com/Mohammedcha/ProxRipper/main/full_proxies/http.txt` - **skip first 50k, take second 50k (50,000-100,000)**
- **Pipeline:** Load persistent dead list -> fetch second 50k -> dead-first filter (remove already dead before validate) -> validate via `httpbin.org/ip` (100 concurrency) -> update dead list (never deleted) -> geolocate working via `ip-api.com/batch` -> save `data/live_proxies.json`, `data/dead_proxies.json`, `country/<CC>/http.txt`
- **Schedule:** Every 1 hour + manual dispatch
- **Dead list:** Shared logic with `habibi-boost` (initially copied 49k dead), persistent per repo

## Data
- `data/dead_proxies.json` - persistent dead proxies (never deleted)
- `data/live_proxies.json` - working proxies with country
- `country/<CC>/http.txt` - per-country sorted
- `country/all_http.txt` - all working
