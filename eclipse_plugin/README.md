# google-java-format Eclipse Plugin

## Enabling

See https://github.com/google/google-java-format#eclipse

## Development

### Prerequisites

If you build a `-SNAPSHOT` build make sure the version in the manifest file uses the qualifier `.qualifier` (that is filled
with a date version qualifier by the tycho plugin) and the `revision` property in the parent pom uses the qualifier `-SNAPSHOT`.
If you build a release make sure to remove `.qualifier`.

Make sure that the jars referenced in `build.properties` and `META-INF/MANIFEST.MF` (in `lib/`)
comply with the set of runtime dependencies required for the core jar.

### Build Dropin

1) Uncomment `<module>eclipse_plugin</module>` in the parent `pom.xml`

2) Run `mvn install`, which will copy the dependences of the plugin to
`eclipse_plugin/lib` and triggers the tycho build that uses the `eclipse_plugin/lib` (because of the
definition in the build.properties file).

3) You find the dropin here: `eclipse_plugin/target/google-java-format-eclipse-plugin-<version>.jar`
