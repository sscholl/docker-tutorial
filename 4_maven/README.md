Run maven container for mvn install

```
# without m2 cache
docker run -it --rm --name my-maven-project -v <PATH_TO_SpringExample>:/usr/src/mymaven -w /usr/src/mymaven maven:latest mvn clean install

rm SpringExample/target/ -r

# with m2 cache
docker run -it --rm --name my-maven-project -v <PATH_TO_SpringExample>:/usr/src/mymaven -v m2cache:/root/.m2 -w /usr/src/mymaven maven:latest mvn clean install
```
