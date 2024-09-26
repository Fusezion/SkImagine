## Future of SkBee
SkBee is now back to being a public repo, https://github.com/ShaneBeee/SkBee, however he has since archived the repo to read only, meaning there
are no longer any updates planned and has been discontinued. Luckily not only is repo wiki back, but it's also possible to find on SkriptHub documentation page.
Since SkBee is archived, I'll be working even harder to releasing this fork of SkBee, with different approaches to some syntax in hopes that it makes it easier to use.

| SkBee Alternatives | Author      | Notes                                                                              | Github Links                                        |
|:-------------------|-------------|------------------------------------------------------------------------------------|:----------------------------------------------------|
| SkBee Continued    | EquipableMC | Newer to java but should be able to<br/>make releases                              | https://github.com/EquipableMC/SkBee-Continued      |
| skript-scoreboards | _tud        | Adds scoreboards, using the same api as SkBee<br/>Wish he handled conflicts better | https://github.com/UnderscoreTud/skript-scoreboards |
| Skript             | SkriptLang  | Will only consist of bukkit api elements                                           | https://github.com/SkriptLang/Skript                |
| N/A                | N/A         | N/A                                                                                | N/A                                                 |

Please note I will only include alternatives that are on GitHub, an example being `skript-bossbars`, this addon is great, but it's not on GitHub.

# SkImagine
SkImagine is an addon with similar elements of SkBee, the key main difference being some features are stripped out, these can be as simple as existing Skript prs exist or implementation isn't worth the effort. An example being bukkit advancements,
not only does this existing api suck and lack useful implementation, but it's bare bones. Bossbars are another example, Skript has a PR for these and will eventually be added without an extra addon being needed, it'll support majority of the same elements if not all,

I am willing to add any removed SkBee element, if I see enough demand, I enjoy new things, but I also don't want to add things that are planned for Skript or already being implemented.

SkImagine was made with stripping down SkBee in mind, however I want to test changes I never did get to for SkBee development so some things are changing such as recipes having a new experimental api,
this api will be changing recipes to use expressions or effects over say entries. This is done to make creation of recipes a more interchangeable recipe sections. I suggest reading the wiki [HERE]() for conversion information.

## Supporting Development/Oneself
I imagine the people who find this will eventually need help or want to know how they can help. While adding examples on SkriptHub will be a start and SkUnity discord being an alternative for personal help they aren't always the best,
as such I'm planning to introduce a new support discord for any of my addons, this discord is currently large WIP and will not be opened for a while longer, so keep on the lookout for a discord invite listed here in the future.

## What about Parity

### Parity Between SkBee
I intend to retain parity for most things however I cannot guarantee this, I want to make syntax flow better or more versatile this means some syntax can change, an already planned example is scoreboards,
I want to allow scoreboard references enabling players to store and reuse them without the addon needing to grab the instance each time
```applescript
# OLD, for sake of showcase plurals are removed
line %number% of scoreboard of %player%
title of scoreboard of %player%
# NEW, for sake of showcase plurals are removed
scoreboard of %player%
socreboard line %number% of %scoreboard%
scoreboard title of %scoreboard%
```
Although unlike `skript-scoreboards` I don't intend to break the api in a way that you can make scoreboard references without a player object attached, this is just unsafe in my honest opinion
Sadly changes do not stop there as more changes, these changes will be documented once they're more defined or handled

### Parity Between Skript
I'm planning to try something new, which I hope more addons will start which is any new commit I make to this addon that consist of bukkit api, I will also start a new skript PR with the feature if it doesn't already exist.
The goal of this design flow is the retain parity between skript release and addon release, skript has recently made their hate of addon syntax clear, why they hate it no clue, but their main takeaway is
that it creates a standard for PRs that add exactly what the addon does and doesn't try to expand it into more areas.

I hate this style of gate keeping and I hate their reasoning the most, addons do what they can and try to keep it as flexible as possible. This is why most addons used expressions over effects, in recent months
skript has pushed the agenda that effects and conditions should be used more often for toggleable/boolean expressions. I can agree to this but only recently. Skript never had a way to convert a condition to a boolean but, now that we can
there is a truth to the fact conditions and effects should be used instead.

Parity between SkImagine and Skript is not always promised, if Skript thinks it's best to expand the api onto something else, like how they are with tab complete, then there's little that I can do.
When syntax like this is added, instead of breaking randomly the syntax will be kept until the next major 0.X.0 release after skript version bump, albeit with a pretty annoying warning message.

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
| Bossbars        |  **Yes**  | There is an available Skript PR located [here]                            |
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
| Teams           |  **Yes**  | There is an available Skript PR located [here]                            |
| Text Components |  **Yes**  | Paper Components > String, prove me wrong                                 |
| Tick Manager    |  **No**   | There is an available Skript PR located [here]                            |
| Villagers       |  **Yes**  | Skript missing this syntax and it's cool                                  |
| Virtual Furnace |  **No**   | Requires stand alone addon, proper implementation                         |
| World Border    |  **Yes**  | There is an available Skript PR located [here], still nice to add         |
| World Creator   |  **Yes**  | Mildly complicated, possible changes from a section                       |

# Syntax Changes

### Mini Messages
The syntax provided here, is just something I'm thinking about and is not 100% guaranteed to be added, I plan to try as hard as I can do add it and changes
will likely be done to syntax design now that I'm wanting to move away from entries as much as possible. If this is kept two variants will be added a structure (entries) and a section (expressions/effects)

Per the request of people changes will be done to making this more human-readable and less dependent on knowing skript syntax
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
