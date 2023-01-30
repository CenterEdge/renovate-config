# renovate-config

Renovate is a dependency update tool https://github.com/renovatebot/renovate

- List of all open pull requets created by Renovate [https://github.com/pulls](https://github.com/pulls?q=org%3ACenterEdge+is%3Apr+is%3Aopen+author%3Aapp%2Frenovate+)
- Configuration documention: https://docs.renovatebot.com/configuration-options
- Presets documentation: https://docs.renovatebot.com/config-presets/
- Run logs: https://app.renovatebot.com/dashboard#github/CenterEdge/
- See any `renovate.json` in our repos for how to add a new Renovate configuration to a repo. Also repos with newly added renovate configs need to be added to github.com/settings/installations --> Integrations --> Applications --> Renovate Configure --> "Only Select Repositories"
- In general, the default `renovate.json` for any repo that is added to Renovate to should look something like this:
```json
{
  "extends": [
    "github>CenterEdge/renovate-config//phoenix/default"
  ],
  "description": "The Renovate configuration presets are in https://github.com/CenterEdge/renovate-config"
}
```


----

- `rangeStrategy` is set to `bump` so minor/patch npm version updates would not be ignored
- `stabilityDays` is helpful to prevent upgrading to packages that have only been released very recently. Such as npm packages are allowed to be removed from the npm repo within a few days of initial release. If we update a third party npm package and then it's removed from npm entirely that would not be good
- When does Renovate update a repository?
  - When the `schedule` is triggered
  - When a renovate.json is changed
  - When the checkbox "Check this box to trigger a request for Renovate to run again on this repository" is checked. This is in the Repositories "Issues" tab --> Dependency Dashboard. However, the Issues tab isn't present in all repositories

----

You can use https://github.com/CenterEdge/TempPackageManagerConcept as a sandbox to test renovate changes without creating PRs or asking anyone permission. Just merge directly into master
