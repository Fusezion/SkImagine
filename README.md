## Future of SkBee
SkBee is now back to being a public repo, https://github.com/ShaneBeee/SkBee, however he has since archived the repo to read only, meaning there
are no longer any updates planned and has been discontinued. Luckily not only is repo wiki back, but it's also possible to find on SkriptHub documentation page.

Since SkBee is archived, I'll be working even harder to releasing this fork of SkBee, with different approaches to some syntax in hopes that it makes it easier to use.
I've received some dislike in how I want to handle mini message builders, so we'll see how that creation goes

# SkImagine
SkImagine is an addon with similar elements of SkBee, the key main difference being some features are stripped out, these can be as simple as existing Skript prs exist or implementation isn't worth the effort. Example being bukkit advancements,
not only does this existing api suck and lack useful implementation but it's bare bones. Another example is bossbars, Skript has a PR for these and will eventually be added without an extra addon being needed. I am willing to add any removed SkBee element
if I see enough demand, I enjoy new things, but I also don't want to add things that are planned for Skript

SkImagine was made as a stripped down version of SkBee in addition to testing changes without explicitly adding to SkBee these changes include
but are not limited to recipe sections based on expressions/effects, nbt no longer having references and merchant villager sections. In addition, after a proper release of this is made, I intend to make PRs to Skript whenever a new feature is added,
this is made as a means to not only retain same syntax between Skript and SkImagine releases but to make updating for the player easier. This also cuts down on bloat of the plugin and focuses on creating more Skript bloat.

Parity between SkImagine and Skript is not always promised, if Skript thinks it's best to expand the api onto something else, like how they are with tab complete, then there's little that I can do.
When syntax like this is added, instead of breaking randomly the syntax will be kept until the next major 0.X.0 release, albeit with a pretty annoying warning message.

I'm a strong believer in breaking changes being good, but I'm also aware that people don't want to update their code when something is removed in favor of another, this coding style is designed to make updates more worthwhile for avid users and meet expectations early.

## Supported Server/Skript Versions
This addon is only ever really planning to support the latest of Skript and Paper, As these are generally the best options for anyone.

### What about Spigot?
I want to limit the amount of times I need to do class check methods, not only does it rely on reflection but it's also just a pointless extra step. Majority of servers and developers
already use Paper, people who don't are usually one of two types.
1. Either are new to skripting and running a local host
2. Wanted to test a new spigot feature while waiting for paper to do their bi-yearly upstream update

### Can I use X Version?
As I've stated above I only intend to support the latest of each version, to help people migrate between versions I have listed below,
the versions of the addon with each paper and skript version supported, along with a url to the release itself.

#### Version Support
| Version | Server Version | Skript Version | Release URL                                           |
|:--------|:---------------|:---------------|:------------------------------------------------------|
| 1.0.0   | Paper 1.21.1   | 2.9.2          | https://github.com/Fusezion/SkImagine/releases/latest |

# SkBee Vs. SkImagine

| SkBee Elements  | Will Add  | Reasoning                                                                 |
|:----------------|:---------:|:--------------------------------------------------------------------------|
| Advancements    |  **No**   | Bukkit lacks a proper implementation, and I don't want unsafe calls       |
| Bossbars        |  **No**   | There is an available Skript PR located [here]                            |
| Bounds          |  **Yes**  | It's a custom implementation, but there's always some use for these       |
| DamageSource    |  **No**   | There is an available Skript PR located [here]                            |
| Displays        | **Maybe** | There is an available Skript PR located [here]                            |
| Fishing         |  **Yes**  | Skript PR Closed & I like Fish                                            |
| GameEvents      |  **Yes**  | Not many uses for most people, but will add for that 0.001%               |
| Generators      |  **Yes**  | Complicated, possible continuation along side world creator               |
| Item Components |  **Yes**  | Skript hasn't added it all yet                                            |
| NBT             |  **Yes**  | Skript-nbt sounded dumb                                                   |
| Objectives      | **Maybe** | There is an available Skript PR located [here]                            |
| Particles       |  **No**   | just use Skript-particle already                                          |
| Raytrace        |  **Yes**  | Future Skript PR more features, some basic systems will be added          |
| Recipes         |  **Yes**  | I like recipes                                                            |
| Scoreboards     |  **Yes**  | Skore dumb                                                                |
| Statistics      |  **Yes**  | Skript PR stale                                                           |
| Structures      |  **Yes**  | There is an available Skript PR located [here], but was told to add       |
| Minecraft Tags  |  **Yes**  | Better Itemtype, items shouldn't be called single                         |
| Teams           |  **No**   | There is an available Skript PR located [here]                            |
| Text Components |  **Yes**  | Paper Components > String, prove me wrong                                 |
| Tick Manager    |  **No**   | There is an available Skript PR located [here]                            |
| Villagers       |  **Yes**  | Skript missing this syntax and it's cool                                  |
| Virtual Furnace |  **No**   | Requires stand alone addon, proper implementation                         |
| World Border    |  **Yes**  | There is an available Skript PR located [here], still nice to add         |
| World Creator   |  **Yes**  | Mildly complicated, possible changes from a section                       |

# Syntax Changes

In the above statement I mentioned some changes to Recipes, NBT and Merchants here is a bit more information about them.

### NBT
NBT will initially release with 2 versions first one being the existing implementation of SkBee with some changes to it,
and another aimed at working how the api intends for us to handle items, entities and more. In addition, this second version
includes a new system called `nbt handlers` and hopefully possibly `nbt proxies` which nbt handles depend on pretty heavily

### Recipes & Merchants
This was initially intended to be released with SkBee's 3.0.0 release for recipes, however was delayed, these changes will be applied
regardless of implementations as they're much better than old effects and more useful sections.

### Text Components
These should see changes more to the base system of mini messages and things like `component lore of %itemtype%` and similar syntax, this
was done to mainly make these flexible but also ensuring syntax can be guessed more easily i.e. prepending `component` into Skript things

- `component lore of player`
- `component display name of player`
- `component name of entity`
- `event-text component`

In the future we could hopefully see these as `set lore of player's tool to text component from """` and use the correct method usages with the WIP Any X api

### Mini Messages
This is just syntax in theory but is something I want to look into creating for server owners
```applescript
on load:
    # In a future Skript version, a SectionExpression might be used in place of the variable section
    create [a] [new] mini[ ]message [instance]:
        variable: {-minimessage::admins}
        debug mode: true
        strict mode: true
        tags:
            [:dis]allow all standard tags
            remove %standardtags% from tags
            add %standardtags% to tags
            create [a] [new] tag[s] %strings%:
                # tags refer to things like <gradient:#ff00ff:#00ffff> and other styling formats
                # this section allows creation of custom ones with their own parser allowing developers more freedom
                # more to this section in the future
                # set result tag to ...
```
