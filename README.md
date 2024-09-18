# SkImagine
SkImagine is an addon with similar elements of [SkBee](https://github.com/ShaneBeee/SkBee), the key main difference being some features are stripped out, these can be as simple as existing [Skript](https://github.com/SkriptLang/Skript) prs exist or implementation isn't worth the effort. Example being bukkit advancements,
not only does this existing api suck and lack useful implementation but it's bare bones. Another example is bossbars, [Skript](https://github.com/SkriptLang/Skript) has a PR for these and will eventually be added without an extra addon being needed. I am willing to add any removed [SkBee](https://github.com/ShaneBeee/SkBee) element
if I see enough demand, I enjoy new things but I also don't want to add things that are planned for [Skript](https://github.com/SkriptLang/Skript)

SkImagine was made as a stripped down version of [SkBee](https://github.com/ShaneBeee/SkBee) in addition to testing changes without explicitly adding to [SkBee](https://github.com/ShaneBeee/SkBee) these changes include
but are not limited to recipe sections based on expressions/effects, nbt no longer having references and merchant villager sections. In addition, after a proper release of this is made, I intend to make PRs to [Skript](https://github.com/SkriptLang/Skript) whenever a new feature is added,
this is made as a means to not only retain same syntax between [Skript](https://github.com/SkriptLang/Skript) and SkImagine releases but to make updating for the player easier. This also cuts down on bloat of the plugin and focuses on creating more [Skript](https://github.com/SkriptLang/Skript) bloat.

Parity between SkImagine and [Skript](https://github.com/SkriptLang/Skript) is not always promised, if [Skript](https://github.com/SkriptLang/Skript) thinks it's best to expand the api onto something else, like how they are with tab complete, then there's little that I can do.
When syntax like this is added, instead of breaking randomly the syntax will be kept until the next major 0.X.0 release, albeit with a pretty annoying warning message.

I'm a strong believer in breaking changes being good, but I'm also aware that people don't want to update their code when something is removed in favor of another, this coding style is designed to make updates more worthwhile for avid users and meet expectations early.

## Future of SkImagine and SkBee
Shane has as of this moment in time confirmed that [SkBee](https://github.com/ShaneBeee/SkBee) isn't returning, in addition to spigot even saying it's discontinued, I plan to continue working on this however when in a usable state only SkriptHub will support documentation.

## Supported Server/Skript Versions
This addon is only ever really planning to support the latest of [Skript](https://github.com/SkriptLang/Skript) and Paper, As these are generally the best options for anyone.

### What about Spigot?
I want to limit the amount of times I need to do class check methods, not only does it rely on reflection but it's also just a pointless extra step. Majority of servers and developers
already use Paper, people who don't are usually one of two types.
1. Either are new to skripting and running a local host
2. Wanted to test a new spigot feature while waiting for paper to do their bi-yearly upstream update


Latest, I couldn't give a rat's ass about your 1.20.4 minecraft server, 1.20.5+ is where money is at, so 1.21+ is the logical solution.

In addition to only supporting the latest minecraft versions, I'll only be supporting paper servers, spigot servers are always looked downed on and make maintaining even more difficult than it needs to be.

### Version Support
| Version | Server Version | Skript Version |
|:--------|:--------------:|:---------------|
| 1.0.0   |  Paper 1.21.1  | 2.9.2          |

# SkBee Vs. SkImagine

| SkBee Elements  | Am Adding | Why Not                                                             |
|:----------------|:---------:|:--------------------------------------------------------------------|
| Advancements    |  **No**   | Lack of bukkit implementation                                       |
| Bossbars        |  **No**   | Skript PR Available                                                 |
| Bounds          |  **Yes**  | Custom implementation not worth effort, but we'll see where it goes |
| DamageSource    |  **No**   | Skript PR Available                                                 |
| Displays        | **Maybe** | Skript PR Available                                                 |
| Fishing         |  **Yes**  | Skript PR Closed & I like Fish                                      |
| GameEvents      |  **Yes**  | Not many uses for most people, but will add for that 0.001%         |
| Generators      |  **Yes**  | Complicated, possible continuation along side world creator         |
| Item Components |  **Yes**  | Skript hasn't added it all yet                                      |
| NBT             |  **Yes**  | skript-nbt sounded dumb                                             |
| Objectives      | **Maybe** | Skript PR Available                                                 |
| Particles       |  **No**   | just use skript-particle already                                    |
| Raytrace        |  **Yes**  | Future Skript PR more features, some basic systems will be added    |
| Recipes         |  **Yes**  | I like recipes                                                      |
| Scoreboards     |  **Yes**  | Skore dumb                                                          |
| Statistics      |  **Yes**  | Skript PR stale                                                     |
| Structures      |  **Yes**  | Was told to by a very forceful man                                  |
| Minecraft Tags  |  **Yes**  | Better Itemtype, items shouldn't be called single                   |
| Teams           |  **No**   | Skript PR available                                                 |
| Text Components |  **Yes**  | Paper Components > String, prove me wrong                           |
| Tick Manager    |  **No**   | Skript PR Available                                                 |
| Villagers       |  **Yes**  | Skript missing this syntax and it's cool                            |
| Virtual Furnace |  **No**   | Requires stand alone addon, proper implementation                   |
| World Border    |  **Yes**  | Skript PR Available, but would like to see                          |
| World Creator   |  **Yes**  | Mildly complicated, possible changes from a section                 |

# Syntax Changes

In the above statement I mentioned some changes to Recipes, NBT and Merchants here is a bit mre information about them.

### NBT
NBT will initially release with 2 versions first one being the existing implementation of [SkBee](https://github.com/ShaneBeee/SkBee) with some changes to it,
and another aimed at working how the api intends for us to handle items, entities and more. In addition, this second version
includes a new system called `nbt handlers` and hopefully possibly `nbt proxies` which nbt handles depend on pretty heavily

### Recipes & Merchants
This was initially intended to be released with [SkBee](https://github.com/ShaneBeee/SkBee)'s 3.0.0 release for recipes, however was delayed, these changes will be applied
regardless of implementations as they're much better than old effects and more useful sections.

### Text Components
These should see changes more to the base system of mini messages and things like `component lore of %itemtype%` and similar syntax, this
was done to mainly make these flexible but also ensuring syntax can be guessed more easily i.e. prepending `component` into [Skript](https://github.com/SkriptLang/Skript) things

- `component lore of player`
- `component display name of player`
- `component name of entity`
- `event-text component`

In the future we could hopefully see these as `set lore of player's tool to text component from """` and use the correct method usages with the WIP Any X api

### Mini Messages
This is just syntax in theory but is something I want to look into creating for server owners
```applescript
on load:
    # In a future skript version, a SectionExpression might be used in place of the variable section
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
