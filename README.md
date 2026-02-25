# Acuity Actions

  Reusable GitHub Actions for Acuity PPM deployments.

  ## Releasing

  When creating a new release:

  1. Create a version tag as usual:
     ```bash
     git tag v6.0.46
     git push origin v6.0.46

  2. Update the floating v6 tag so all workflows pick up the new version:
  git tag -f v6 v6.0.46
  git push origin v6 --force
