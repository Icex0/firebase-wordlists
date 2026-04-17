# firebase-wordlists

Wordlists for black-box fuzzing of Firebase targets. Names are mined from public GitHub source code, not guessed.

Used by [OpenFirebase](https://github.com/Icex0/OpenFirebase).

## Cloud Functions (httpsCallable)

Callable function names extracted from public JS/TS repos by searching for `.httpsCallable(...)`, `functions.httpsCallable(...)`, and the v9 modular `httpsCallable(functions, '...')` patterns. After extraction, names are grouped by the number of distinct repositories they appear in.

| File | Count | Contents |
|---|---|---|
| `cloud-functions/top-50.txt` | 50 | Highest-signal names, ranked by distinct-repo count. Good for quick passes. |
| `cloud-functions/top-250.txt` | 250 | Broader common-names list, same ranking. |
| `cloud-functions/top-500.txt` | 585 | Every name seen in at least 2 different repos, ranked by distinct-repo count. |
| `cloud-functions/full.txt` | 6,683 | Every extracted name, including one-offs. Alphabetical. Noisy but exhaustive. |

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

## Firestore Collections

Collection names extracted from public JS/TS repos by searching for `.collection('...')`, `collection(db, '...')`, `collectionGroup(...)`, `doc(db, 'collection/...')`, and `match /collection/{id}` blocks.

| File | Count | Contents |
|---|---|---|
| `firestore-collections/top-50.txt` | 50 | Highest-signal names, ranked by distinct-repo count. |
| `firestore-collections/top-250.txt` | 250 | Broader common-names list, same ranking. |
| `firestore-collections/top-500.txt` | 516 | Every name seen in at least 3 different repos, ranked by distinct-repo count. |
| `firestore-collections/full.txt` | 4,633 | Every extracted name, including one-offs. Ranked by distinct-repo count. Noisy but exhaustive. |

### Top 15 (by distinct repos)

```
1718  users
 204  posts
 179  products
 178  messages
 151  orders
 129  notifications
 111  events
  97  projects
  97  rooms
  96  categories
  91  chats
  86  comments
  80  tasks
  77  transactions
  76  members
```