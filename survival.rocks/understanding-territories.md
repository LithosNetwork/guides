# Understanding territories

Territories are player-made settlements where players join together and build a small community. You can check out existing territories with `/territories`.

## Roles

Residents in a territory can have the following roles:

- **Resident:** A player who is a member of a territory.
- **Archon:** The leader of a territory. A territory can have multiple archons, but a player can only be archon of one territory.
- **Vizier:** A trusted admin of the archon(s), with fewer permissions than an archon.
- **Constable:** A role for players who help keep order in the territory, with limited permissions.

## Claiming chunks

A territory can only claim chunks at one location. Every claimed chunk has to touch another claimed chunk, so you cannot have separate regions. This keeps a territory a real community in one place.

You get 8 chunks to start off with, and 8 extra chunks for every resident. Example: A territory with 5 residents can claim 8 + (5 × 8) = 48 chunks.

Archons and viziers can access all claims within the claimed chunks of their territory.

## Joining a territory

A territory can be set up in two ways:

- **Public:** Everyone can join.
- **Invite only:** You need an invite from an archon or vizier of the territory before you can join.

To join a territory, you can either get invited, or join a public territory with `/territory join <name>`. You can be a resident of 3 territories at most! A territory can also have a join cost, or be free to join. Check the territory first, so you know what you pay. You can do this with `/territory info <name>`.

### Becoming a resident by buying a plot

You automatically become a resident of a territory when you buy a plot inside its claim. This only happens when all of these are true:

1. The chunk is claimed by the territory.
2. The join cost of the territory is 0.
3. The buyer is not already resident for 3 territories: Players can be resident of 3 territories at most. The sale is canceled if the player is already resident of 3 territories, if the claim is inside a territory.
4. One of the private shareholders of the selling company has invite permissions.

Archons can change this with `/archon settings plot-sale-become-resident`.

## Territory chat

Every territory has its own chat, just for its residents. Use `/t chat` to talk with them.

### Discord

Some territories have their own Discord server. Find the Discord server invite of your territory with `/t discord`.
