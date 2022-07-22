# renovate-config

Renovate is a dependency update tool https://github.com/renovatebot/renovate

- Configuration documention: https://docs.renovatebot.com/configuration-options
- Presets documentation: https://docs.renovatebot.com/config-presets/
- Run logs: https://app.renovatebot.com/dashboard#github/CenterEdge/
- See any `renovate.json` in our repos for how to add a new Renovate configuration to a repo. Also new repos need to be added to github.com/settings/installations --> Integrations --> Applications --> Renovate Configure --> "Only Select Repositories"


----

- `rangeStrategy` is set to `bump` so minor/patch npm version updates would not be ignored
- `stabilityDays` is helpful to prevent upgrading to packages that have only been released very recently. Such as npm packages are allowed to be removed from the npm repo within a few day of initial release. If we update a third party npm package and then it's removed from npm entirely that would not be good.
