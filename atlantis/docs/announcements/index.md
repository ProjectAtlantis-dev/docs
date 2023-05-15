# Announcements

## May 15 @ Lift99 - Meetup: Hackage Setup and Administrivia

This meeting will be a technical prelim to go over ProjectAtlantis setup. This will essentially be the opposite of the last meeting i.e. get into the weeds of technical details and answer questions

In a nutshell, we've decided to open source the Atlantis chatbus backend so you know exactly what your bots are talking to. Even if you don't care about Atlantis specifics you may want to be involved since we will be tackling things your next enterprise project may be facing anyway

If you want to be a contributor please contact us in Discord !!

You can expect to have table(s) to put your laptop on and/or use a meeting room (typically the first few meetings are sparsely attended because some may prefer to skip past this sausage making but who knows). Does anyone want external monitors?

Anyway, we don't want to be making a ton of decisions in a vacuum. If you have suggestions, please share !!!

Having said that lol ... so far (all subject to your input and thoughts):

(1) DOCS - I set up an mkdocs server as primary doc store (with mermaid support etc)

(2) ARCH - I've split back end services btw Node/Typescript and Python so we have flexibility to use either. Planning on websockets for bi-directional communication. Bot client support will be both Typescript and Python. Python has all the latest libraries but type checking is a rolling mess (vale, black, ruff, mypy, pydantic etc.). A lot of these AI projects also seem to be Python/TS lang mix. Of course, you can use anything for your bots if you are running on your own hardware

(3) DATA - Postgres tables for now so the data model is understandable but it's also possible a lot of trad columns may be replaced by narrative text. See below for persistent components.

(4) VECTOR - leaning towards ChromaDB w Cohere embeddings for vector stuff; looked at Supabase but seemed a bit over-engineered

(3) + (4) COMPONENTS - for now (a) map store,(b) a resource store (incl inventory) and (c) primary log/chat stream (what Stanford calls the memory stream)

(5) METHOD - okay now things get strange. Since this is an AI world, writing code old school is rapidly getting outdated and that means OSS projects will change too. Been looking at AI codegen projects like e2b and smol (there are probably others). Given the highly opinionated output of codegen, we could also just roll our own for Atlantis. If we make everything basically services, it is possible to just load small modules into context memory and let AI decide what code changes need to be applied ... and then apply them. The main drawback is that contributors will probably need GPT4 access (we can probably set up a license pool but not sure if that will annoy OpenAI - heck they are getting revenue regardless). Same goes for Claude or Bard API access (still invite only). We should discuss

(6) Items (1) and (5) may end up being related because I'm seeing projects starting to use markdown as the primary coding language. It's either that or some strange interleaving of Python/Typescript/text or some Jupyter-esque thing. Very interesting question. On my prior project I went down this rabbit hole but VSCode extensions and fences will only get you so far

(7) Items (1) and (3) may also end up being related as well. I started playing w mermaid as the primary data language at least for map design because GPT4 is pretty good at converting stuff in and out of JSON

That is probably more than enough to consider - if you miss this meeting don't worry we may try to sneak in some more on a weekly basis (although Thurs tends to be a busy night) until we get hackthon logistics nailed. As things settle down, we will get into an operational tempo and can do more things online


## May 4 @ Lift99 - 9Meetup: Bot Builders Kickoff

Lots of great food & drink !!