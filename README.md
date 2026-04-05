# Trello API Postman Test Suite

[![Run in Postman](https://run.pstmn.io/button.svg)](https://rogerarboles-5798269.postman.co/workspace/Roger-Arboles-Sanchis's-Workspa~c1867661-9f7b-4b76-82bf-815120120d70/collection/53749011-af41bec6-9299-441c-bf86-b4f638a04b82?action=share&source=copy-link&creator=53749011)
![API Tests](https://github.com/ruchi546/Trello-API-Postman/actions)

Practice project of API testing with Postman.
Tests Board → List → Card → Checklist lifecycle against the real Trello API.

## CI/CD
Tests run automatically on every push via GitHub Actions.
Credentials are stored as GitHub Secrets.

## What's tested
- Board: Create, Get, Update, Delete
- Lists: Create, Get, Archive
- Cards: Create, Get, Update, Delete
- Checklists: Create, Get, Add item, Delete

## How to import
1. Download `Trello API Tests.postman_collection.json`
2. Open Postman → Import → Upload the file
3. Set the collection variables: `baseURL`, `key`, `token`

## How to run
```bash
newman run Trello_API_Tests.postman_collection.json \
  --env-var "baseURL=https://trello.com" \
  --env-var "key=YOUR_KEY" \
  --env-var "token=YOUR_TOKEN" \
```

## What I learned
- Request chaining with collection variables
- E2E lifecycle testing (create → verify → delete)
- Running tests in CI with GitHub Actions

## Notes
- The suite creates real Trello resources and deletes them after each run (full teardown)
- Requires a free Trello account and API credentials
