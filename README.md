# active-forks
Might turn it into an app

Query I use to get the last active fork of an unmaintained project


```graphql
query { 
  repository(
    owner: "gabrielmoncea"
    name: "react-native-temaplate"
  ) {
    name
    forkCount
    forks(
      first: 25 # 100 limit
      orderBy: { field: PUSHED_AT, direction: DESC }
    ) {
      totalCount
      nodes {
        url
      }
    }
  }
}
```
