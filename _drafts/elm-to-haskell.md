# Learning Haskell... With Elm!

Haskell has an intense learning curve. Anyone who's gotten started with it knows this well. The shangri-la of pure, functional programming languages has garnered a nasty reputation for inaccessibility.

But Haskell is also an incredibly interesting and, believe it or not, useful language for building fast, reliable applications. Learning it will both add a new tool to your belt and change the way you program in more familiar languages.

Haskelll was the third programming language I began learning; that was several years ago, and I still consider myself an amateur. It's tough stuff. After learning the basics I hit a roadblock. And then I found Elm.

Elm, in contrast to Haskell, has generated a lot of positive press around not only its reliability, but also its approachability. It's a language built with the programmer's experience as a top priority. After familiarizing myself with Elm in a relatively short amount of time, I felt empowered to dust off the ol' Haskell tomes and get back to it.

And guess what? It was a lot easier!

Elm borrows a lot of ideas from Haskell; the similarities are abundant. By focusing on usability, Elm familiarizes you with FP concepts that are traditionally hard to learn or teach. If you learn best by doing, Elm is the ramp you need to ease into Haskell's learning cliff.

Let's start with some basics.

[Elm Installation](https://guide.elm-lang.org/install.html)
[Haskell Installation](https://www.haskell.org/platform/)

## The Similarities

### Comments

Every programming language needs comments, right? Good news: comments in Haskell and Elm look exactly the same.

```haskell
-- They both look like this :D
{- Or they can extend to
   multiple lines!
-}
```

Fair enough. What else is the same?

### Functions

Haskell and Elm both draw most of their syntax and many of their core concepts from a common ancestor called [ML](https://en.wikipedia.org/wiki/ML_(programming_language)). This means that function definitions and type declarations look remarkably similar in the two languages. 

```haskell
-- elm
stringThings : String -> String -> String
stringThings stringA stringB = ~~some definition~~

-- haskell
stringThings :: String -> String -> String
stringThings stringA stringB = ~~some definition~~
```

Functions in both languages are declared in the same way and automatically curried, meaning that you can apply arguments to them one at a time rather than all at once. They can also be applied and composed in much of the same way (but more on that later).

You'll notice one difference in the above example: Elm type signatures are denoted with a single `:`, while Haskell opts for the double `::`. It'll take a bit of getting used to. In Haskell and Elm, type declaration and array concatenation are swapped.

```haskell
-- elm
[1,2,3,4] == 1 :: 2 :: 3 :: 4 :: []

-- haskell
[1,2,3,4] == 1 : 2 : 3 : 4 : []
```

Yes, it's annoying, but stick with me!

### Lambdas, Types and Records

You can declare anonymous functions in Haskell and Elm in the same way.

```haskell
-- this is valid in both languages!
(\a b -> a + b) 2 4
```

The way you declare new types in Haskell is also very similar to Elm.

```haskell
-- elm
type alias Name = String
type ForceUser = Jedi Name | Sith Name

-- haskell
type Name = String
data ForceUser = Jedi Name | Sith Name
```

Again, the name swapping is sort of confusing, but you can see support for type aliases (`type`), and union/sum types (`data`) in Haskell. 

You can also use record syntax when declaring types in Haskell; although, unlike in Elm, Haskell records are not first-class citizens and can be thought of as syntactic sugar on top of a union type.

```haskell
-- haskell
data Wookie = Wookie { name :: String
                     , weapon :: Weapon
                     , fuzzy :: Bool
                     }

chewie :: Wookie
chewie = Wookie { name = "Chewbacca"
                , weapon = Bowcaster
                , fuzzy = True
                }
```

## The Differences

### Cases vs. Pattern Matching and  Guards

In Elm, your primary tool for matching on sum types and destructuring arguments is the `case` statement.

```haskell
-- elm
greet : ForceUser -> String
greet user =
  case user of
    (Jedi name) ->
      "Greetings, Master " ++ name
    (Sith name) ->
      "I feel the dark side in you, " ++ name
```

Haskell has a number of constructs you can use to achieve the same end. Case statements are supported using exactly the same syntax, though you may also want to consider [pattern matching.](https://en.wikibooks.org/wiki/Haskell/Pattern_matching) Pattern matching is a concise, powerful Haskell feature that isn't supported by Elm. Like Elm's cases, it also enables argument destructuring.

```haskell
-- haskell
greet :: ForceUser -> String
greet (Jedi name) = "Greetings, Master " ++ name
greet (Sith name) = "I feel the dark side in you, " ++ name
```

There is also an alternative syntax for conditional logic in Haskell called [guards](https://en.wikibooks.org/wiki/Haskell/Control_structures#if_and_guards_revisited). They're useful as an alternative to `if/else` when comparing values rather than matching sum types. They look like this:

```haskell
-- haskell
betweenTwoAndSix :: Int -> Bool
betweenTwoAndSix num
  | num < 2   = False
  | num > 6   = False
  | otherwise = True
```

### Let/In vs. Where

In Elm, you can declare scoped values local to your function using `let/in` syntax.

```haskell
-- elm
addTwo : Int -> Int
addTwo num =
  let
    numToAdd = 2
  
  in
    num + numToAdd
```

Haskell supports the same syntactic construct and adds another called `where`. The following two function definitions are equivalent:

```haskell
-- haskell
addTwo :: Int -> Int
addTwo num =
  let numToAdd = 2
  in num + numToAdd

addTwoWhere :: Int -> Int
addTwoWhere num = numToAdd + num
  where numToAdd = 2
```

In Haskell, as in Elm, white space matters when using these constructs!

### Application and Composition

Finally, let's talk about operators. In Elm, you may be familiar with `<|` and `|>` as directional function application operators (do everything on this side first). Basic Haskell (as defined by GHCI's `Prelude`) only supports right-associative function application with `$`. In order words, Elm's `<|` == Haskell's `$`.

In Elm we also have `<<` and `>>`, which we use to compose functions. Haskell's equivalent is called the "dot operator" and defines right-associative composition. Elm's `<<` == Haskell's `.`.

```haskell
-- elm
addTwo = (+) 2
addThree = (+) 3
addFive = addTwo << addThree
addTenThenAddFiv num = addFive <| num + 10

-- haskell
addTwo = (+) 2
addThree = (+) 3
addFive = addTwo . addThree
addTenThenAddFiv num = addFive $ num + 10
```

Note: There are other Haskell libraries that add left-associative appication and composition, but we're going to stick to the `Prelude` for now. 

## Review

Here's a handy table comparing different syntaxes and features in Haskell and Elm:

|elm|haskell|
|--|--|
| `-- one-line comment` | `--one-line comment` |
| `{- multi-line comment -}` | `{- multi-line comment -}`|
| `func : String -> String` | `func :: String -> String` |
|`1 :: 2 :: 3 :: []`|`1 : 2 : 3 : []`|
|`(\a b -> a + b) 2 4`|`(\a b -> a + b) 2 4`|
|`type alias Name = String`|`type Name = String`|
|`type ForceUser = Jedi | Sith`|`data ForceUser = Jedi | Sith`|
|`addFive <| num + 10`|`addFive $ num + 10`|
|`addTwo << addThree`|`addTwo . addThree`|

## What Else?

Of course, because Haskell has been in development about 20 years longer than Elm has, it has a great berth of features that aren't a part of Elm. The purpose of this post is to get you familiarized with the basics and show that if you know Elm, you're already a good chunk of the way there.

Haskell's "Type Classes" define constraints around groups of types and are a big part of what makes the language so powerful. If you've seen the `comparable` keyword in Elm, you already have an idea of what a Type Class is: it groups all of the types that can be compared (`String`, `Int`, `Float`, `Tuple`, etc) and allows type signatures to leverage that grouping. In Haskell, you can define these groupings yourself or add your own types to them. In addition, each Type Class comes with free utility functions!

If you've been using Elm for a while, you might have noticed that a number of the core libraries' modules have a `map` function with a similar type signature. How this function relates to Haskell's type classes will be the subject of the next blog post!

