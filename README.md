# test-ember-cli-update

Testing ember-cli-update to see if it updates the ember-cli-update.json file
when migrating from ember-cli@3.26 to ember-cli@3.27.

Manual reproduction steps:

1. `npx ember-cli@3.26.0 new test-ember-cli-update`
2. `npx ember-cli-update --package ember-cli --blueprint app --to 3.27.0-beta.1`
3. Check `ember-cli-update.json` and `ember-cli-build.js`

At the time of writing, the `ember-cli-build.js` includes Embroider "things"
but the `config/ember-cli-update.json` does not include `--embroider` flag (and
therefore the Embroider packages are missing from `package.json`).
