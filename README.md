# firebase-wordlists

Wordlists for black-box fuzzing of Firebase targets. Names are mined from public GitHub source code, not guessed.

## Cloud Functions (httpsCallable)

Callable function names extracted from public JS/TS repos by searching for `.httpsCallable(...)`, `functions.httpsCallable(...)`, and the v9 modular `httpsCallable(functions, '...')` patterns. After extraction, names are grouped by the number of distinct repositories they appear in.

| File | Count | Contents |
|---|---|---|
| `top-50.txt` | 50 | Highest-signal names, ranked by distinct-repo count. Good for quick passes. |
| `top-250.txt` | 250 | Broader common-names list, same ranking. |
| `top-500.txt` | 585 | Every name seen in at least 2 different repos. Sorted alphabetically. |
| `full.txt` | 6,683 | Every extracted name, including one-offs. Alphabetical. Noisy but exhaustive. |

## Planned

- **Firestore collections** — collection names mined from `collection(...)`, `.collection('...')`, `doc(db, 'collection/...')`.