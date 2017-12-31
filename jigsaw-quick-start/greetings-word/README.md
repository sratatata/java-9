### Greetings World ###

#### Compilation

```bash
javac -d mods/org.astro src/org.astro/**.java
```
is shorter version for command listed in [tutorial](http://openjdk.java.net/projects/jigsaw/quick-start#greetingsworld).

### Multi-module compilation ###

In'my opinion it's better to use: 

```bash
javac -d mods --module-source-path src src/**.java 
```

This command do the same as one in [tutorial](http://openjdk.java.net/projects/jigsaw/quick-start#multimodulecompile), but works on 'fish'.

### Packaging ###

#### org.astro module

``` bash
jar --create --file=mlib/org.astro@1.0.jar \
  --module-version=1.0 -C mods/org.astro .
```

-C - localization of .class files

#### com.greetings

```bash
jar --create --file=mlib/com.greetings.jar \
  --main-class=com.greetings.Main -C mods/com.greetings .
```
