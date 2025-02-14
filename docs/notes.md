## Notes 17/08/23
- KV stores should not necessarily be reused between bank-vaults and secret-sync
- Check how external KMS implemented their providers to get idea about how to move forward
- Mapping function should be handled by provider
- Rules API should allow options on an individual secret level (e.g. merge, transform, concat...) via e.g. templating
- Enable path for multi-destination source/dest if optimal (changes to rules API will have to change)
- Have one "global" synchronization configuration file
- Load configurations for sources/dests from e.g. Kubernetes CRs (check how external secrets k8s works to enable support for more KV stores)
- Documentation (stress the importance of early version)

Priority:
- Ability to have rules api for secrets on individual level (can be added later)
- Add more providers (e.g. AWS, k8s)
- Secret store (actually: set store) != KV store

## Notes 30/08/23
- Target audience: SRE, Devs
- Query testing: makes no sense since it is difficult and cannot cover everything
- Add support for pseudo-template (e.g. bloblang) for transformations
- Add support for secret value transformations (not a priority)
- Add dry run option (does not perform API to sync to dest)
- CronJob for testing the sync in k8s (example)
- Add k8s auth support for stores (e.g. from a path to service file)
- Create validator to check if the plan is valid (without doing the API calls, but use dummy stores)
- Transform testing strategy example: have a map for dummy source as input, have a plan (dynamic), and have expected output for synced secrets
- Write a walkthrough for overall usage (as a CLI or CronJob)
- Use slog package for logging

Priority:
- Add support for pseudo-template (e.g. bloblang) for transformations
- Create validator to check if the plan is valid (without doing the API calls, but use dummy stores)
- CronJob for testing the sync in k8s (example)
- Add dry run option (does not perform API to sync to dest)
