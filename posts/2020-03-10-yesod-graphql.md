As a preface, I am learning Yesod and trying to better my understanding of Haskell. There is likely a deeper understanding that could be gained from someone else writing this post. I will try my best to present everything as accurately and clear as possible. YMMV.

This post assumes you have at least a vague understanding of Yesod's routing as well as GraphQL. If you would like a refresher on either, you can visit the following links as a jumping off point

* https://graphql.org/learn/

* https://www.yesodweb.com/book/basics#basics_routing

Now that we're all caught up, we can set up a GraphQL route within Yesod. Instead of using a pre-defined stack Yesod template, I'm going to set up a Yesod application using a basic foundation (:sunglasses:) to reduce this down to its barest parts.

Here is the file you should start with if you want to follow along with this blog post.

```haskell
{-# LANGUAGE OverloadedStrings     #-}
{-# LANGUAGE QuasiQuotes           #-}
{-# LANGUAGE TemplateHaskell       #-}
{-# LANGUAGE TypeFamilies          #-}
import           Yesod

data LibraryApp = LibraryApp

mkYesod "HelloWorld" [parseRoutes|
/ HomeR GET
|]

instance Yesod LibraryApp

getHomeR :: Handler Html
getHomeR = defaultLayout [whamlet|Hello World!|]

main :: IO ()
main = warp 3000 LibraryApp
```

In reality, it doesn't matter if you use the above code or a stack template because we won't really be changing much; however, I'd like to give a code-complete representation at the end that shows the whole picture as best as I can.

# Clean up the base template above to be an API

# Add GraphQL Route

# Add GraphQL Types from a separate File

# Add GraphQL Types in the same file

# Discuss the issues with `encode` and `toJSON` without JSONResponse

# Potentially discuss the Scotty example and why it works

# Present Client CURL thta works

# Consider Trying out the TypedContent type class as an example, but reiterate that it doesn't really fit since we aren't dealing with a different conent type (spills implementation details)

# Present finished copy along with the stack template repo