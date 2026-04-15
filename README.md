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

### Top 15 (by distinct repos)

```
 70  addAdminRole
 65  ext-firestore-stripe-payments-createPortalLink
 46  createUser
 45  deleteUser
 38  createCheckoutSession
 35  sendEmail
 30  generateUploadUrl
 24  getVideos
 22  createPaymentIntent
 18  deleteUserAccount
 17  cancelSubscription
 17  createStripeCheckoutSession
 17  deleteAccount
 17  setUserRole
 15  sendMessage
```

## Planned

- **Firestore collections** — collection names mined from `collection(...)`, `.collection('...')`, `doc(db, 'collection/...')`.