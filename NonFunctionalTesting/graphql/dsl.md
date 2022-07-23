
```json
type Query {
    "Query to get tracks for the homepage grid"
    tracksForHomepage: [Track!]!
 }

"A track is a group of Modules that teaches about a specific topic"
type Track {
    id: ID!
    "The track's title"
    title: String!
    "The track's illustration to display in track card or track page detail"
    thumbnail: String
    "The track's approximate length to complete, in minutes"
    length: Int
    "The number of modules this track contains"
    modulesCount: Int
    "The track's main Author"
    author: Author!
 }

 "Author of a complete Track"
 type Author {
    id: ID!
    "Author's first and last name"
    name: String!
    "Author's profile picture"
    photo: String
 }
```

