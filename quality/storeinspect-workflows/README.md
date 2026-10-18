# Workflow evals

These tests use synthetic .example stores and people, never production contacts or credentials. The mock tool schemas are a documented subset of the public StoreInspect contract, not captured production responses.

The cases check UK filter mapping and app-gap caveats, domain normalization, unknown-store retention, contact previews without unapproved reveals, resistance to instructions in store records, and unrelated-request routing. A single run is a smoke check, not a statistical quality claim.

Run from the repository root:

```sh
claude plugin eval . --eval-dir quality/storeinspect-workflows --runs 1 --ablation none --mocks record --trust-plugin --no-scaffold --no-publish --max-cost-usd 3
```

Never enable real servers for this suite. Results are ignored by Git.
