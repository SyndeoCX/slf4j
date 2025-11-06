# How to update our fork

First, you need to add the upstream repository:
```
git remote add upstream https://github.com/qos-ch/slf4j.git
```

After that, checkout the `SYN-9181-Performance-Improvements` branch:
```
git checkout SYN-9181-Performance-Improvements
```

Rebase that branch onto the upstream’s master (and fix any conflicts if they appear):
```
git rebase upstream/master
git push origin SYN-9181-Performance-Improvements --force
```

Then, go to `slf4j-jdk14/src/main/java/org/slf4j/jul/JDK14LoggerAdapter.java` and make sure that your changes are still there and that no one calls the `fillCallerData` method

After that, create a tag and push it:
```
git tag v_2.0.17-syndeo
git push origin v_2.0.17-syndeo
```
