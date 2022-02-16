# active-forks
Might turn it into an app

Query I use to get the last active fork of an unmaintained project.
Try it ouy in the [github graphql explorer](https://docs.github.com/en/graphql/overview/explorer)


```graphql
query { 
  repository(
    owner: "gabrielmoncea"
    name: "react-native-template"
  ) {
    name
    forkCount
    forks(
      first: 25
      orderBy: { field: PUSHED_AT, direction: DESC }
    ) {
      totalCount
      nodes {
        url
        licenseInfo{
          name
        }
      }
    }
  }
}
```
