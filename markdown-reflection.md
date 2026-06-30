# Pokemon card game
The Pokémon Trading Card Game, or Pokémon TCG, is a collectible card game where players build decks using Pokémon, Trainer, and Energy cards, then battle by attacking, evolving Pokémon, using items, and trying to take all their Prize Cards before the opponent does. It is based on the Pokémon video games, but instead of controlling Pokémon on a screen, you use cards with different attacks, HP, weaknesses, and strategies. People play it competitively in tournaments, casually with friends, or collect cards for the artwork, rarity, nostalgia, and value.

## Origin of the card game
1. 1996 The idea: After Game Freak released Pokémon Red and Green for the Nintendo Game Boy in February 1996, Pokémon became an instant hit in Japan. The creators wanted a tabletop game where players could battle and collect Pokémon outside of video games.

1. October 20, 1996 – First release: The Pokémon Trading Card Game launched in Japan. It was designed by Creatures Inc., led by Tsunekazu Ishihara and collaborators including Kouichi Ooyama and Takumi Akabane. It was originally published by Media Factory.

1. 1998–1999 – Worldwide explosion: The game came to North America, where Wizards of the Coast (the company behind Magic: The Gathering) published the English cards. The first English Base Set released in January 1999 and quickly became one of the world's most popular trading card games.

1. 2003 onward: Publishing rights outside Japan were transferred to The Pokémon Company International, which still publishes the game today.

## My favorite pokemon sets
- Team Up
- Unified Minds
- Prismatic Evolutions
- Skyridge

## The most expensive Pokemon card
Pikachu Illustrator (1998 Japanese Promo)
Read the [2026 most valuable Pokemon guide](https://finance.yahoo.com/news/top-10-most-valuable-pok-235612525.html?guccounter=1&guce_referrer=aHR0cHM6Ly93d3cuZ29vZ2xlLmNvbS8&guce_referrer_sig=AQAAAF86DAcn_tDyx8Fxrhj4z3COpr6wTyWeE9iaVuEEs8BJq1BFsiQx84x7iygXQfGDtTmCWP3d7h6KJMTOl2ztb8QnFh8JvV7KnEK0U6ai9CR836ydkrce99v8oXw5otA5SqwO_I-gMj2mmbKfq4K3crwwL-uVrtqoVdPSPHcjfc2I)

## My most valuable cards
- [x] Gengar and Mimikyu GX rainbow- $377
- [x] Gengar and Mimikyu GX normal art- $335
- [x] Aerodactyl V alt art- $228

## A card I want
- [ ] Unbreon VMAX alt art (moonbreon) $2,800
![Moonbreon evolving skies](https://tcgplayer-cdn.tcgplayer.com/product/246723_in_1000x1000.jpg)

```html
<div id="pokemon-gallery"></div>

<script>
const sets = [
  "Evolving Skies",
  "Team Up",
  "Prismatic Evolutions",
  "Ascended Heroes"
];

const cardsPerSet = 8;

async function getTopCards(setName) {
  const url = `https://api.pokemontcg.io/v2/cards?q=set.name:"${setName}"&pageSize=250`;

  const res = await fetch(url);
  const json = await res.json();

  return json.data
    .map(card => {
      const prices = card.tcgplayer?.prices || {};
      const price =
        prices.holofoil?.market ||
        prices.reverseHolofoil?.market ||
        prices.normal?.market ||
        prices["1stEditionHolofoil"]?.market ||
        prices.unlimitedHolofoil?.market ||
        0;

      return {
        name: card.name,
        image: card.images.large,
        price,
        set: card.set.name
      };
    })
    .filter(card => card.price > 0)
    .sort((a, b) => b.price - a.price)
    .slice(0, cardsPerSet);
}

async function buildGallery() {
  const container = document.getElementById("pokemon-gallery");

  container.innerHTML = `
    <style>
      #pokemon-gallery {
        font-family: Arial, sans-serif;
        background: #111;
        color: white;
        padding: 20px;
      }

      .set-title {
        color: gold;
        margin-top: 30px;
      }

      .gallery {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(170px, 1fr));
        gap: 18px;
      }

      .card {
        background: #222;
        border-radius: 12px;
        padding: 12px;
        text-align: center;
        box-shadow: 0 0 10px black;
      }

      .card img {
        width: 100%;
        border-radius: 8px;
      }

      .name {
        font-weight: bold;
        margin-top: 10px;
      }

      .price {
        color: #00ff99;
        font-size: 18px;
        margin-top: 5px;
      }
    </style>

    <h1>Most Expensive Pokémon Cards</h1>
  `;

  for (const set of sets) {
    const title = document.createElement("h2");
    title.className = "set-title";
    title.textContent = set;
    container.appendChild(title);

    const gallery = document.createElement("div");
    gallery.className = "gallery";
    container.appendChild(gallery);

    try {
      const cards = await getTopCards(set);

      if (cards.length === 0) {
        gallery.innerHTML = "<p>No cards found for this set.</p>";
        continue;
      }

      cards.forEach(card => {
        gallery.innerHTML += `
          <div class="card">
            <img src="${card.image}" alt="${card.name}">
            <div class="name">${card.name}</div>
            <div class="price">$${card.price.toFixed(2)}</div>
          </div>
        `;
      });
    } catch (err) {
      gallery.innerHTML = "<p>Error loading cards.</p>";
      console.error(err);
    }
  }
}

buildGallery();
</script>
```

## Pokemon "Team Up" set value over time
| Year | Approx. Team Up Pack Price | Increase From Release Price | Notes |
|---|---:|---:|---|
| 2019 | $4–$5 | 1x | Normal retail era; packs were still widely available. |
| 2020 | $8–$12 | 2x–3x | Started rising after Team Up became harder to find. |
| 2021 | $18–$30 | 4.5x–7.5x | Pokémon boom pushed Sun & Moon sealed prices up fast. |
| 2022 | $30–$45 | 7.5x–11x | Supply kept drying up; Team Up became a premium set. |
| 2023 | $45–$65 | 11x–16x | Demand stayed strong because of Latias & Latios GX and other tag team cards. |
| 2024 | $60–$80 | 15x–20x | Older sealed Sun & Moon packs became harder to find. |
| 2025 | $75–$100 | 19x–25x | Loose packs often sold near modern premium vintage levels. |
| 2026 | Around $100 | About 25x | Current loose pack estimate is about $99.99 on PriceCharting. |

\# Team Up Pack Prices

## Preview fix
- My fenced code block didn't originally display due to formatting
Save my file as `POKEMON.md`.
