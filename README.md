# Acuity Actions

Reusable GitHub Actions for Acuity PPM deployments.

## Ruby Runtime Compatibility

Ruby-based actions resolve Ruby from the consumer's `.ruby-version` and Bundler
from its `Gemfile.lock`. Actions that start CodeBuild also accept optional
`RUBY_VERSION` and `BUNDLER_VERSION` overrides. Existing consumers therefore keep
their current versions without action-level runtime defaults.

Consumers migrating to Ruby 4 should pass exact versions:

```yaml
with:
  RUBY_VERSION: "4.0.6"
  BUNDLER_VERSION: "4.0.16"
```

## Releasing

When creating a new release:

1. Create a version tag as usual:

   ```bash
   git tag v6.0.52
   git push origin v6.0.52
   ```

2. Update the floating `v6` tag after backward-compatibility validation:

   ```bash
   git tag -f v6 v6.0.52
   git push origin v6 --force
   ```
