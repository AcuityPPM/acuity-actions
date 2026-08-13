# Acuity Actions

Reusable GitHub Actions for Acuity PPM deployments.

## Ruby Runtime Compatibility

Ruby-based actions resolve Bundler from the consumer's `Gemfile.lock`. Actions that
start CodeBuild accept optional `RUBY_VERSION` and `BUNDLER_VERSION` inputs. The
default Ruby remains `3.2.2` during the Ruby 4 migration window so existing
consumers remain compatible.

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
