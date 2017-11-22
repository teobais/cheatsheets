### Versioning
- Update pom versions in a multi-module project: `mvn versions:set -DnewVersion=15.4.2.1 -DgenerateBackupPoms=false` ; if the last argument is not provided, for each one of the changed poms a `.backup` file will be created.
