# Random Pokémon Battle Web App

## The Idea and Purpose Behind It
This web app allows users to engage in a random Pokémon battle by fetching two random Pokémon from the PokéAPI. The app compares their stats and determines a winner based on their attack power.

## Basic Features
- **Random Pokémon Selection:** Fetches two random Pokémon from the API.
- **Battle System:** Compares the attack stats of both Pokémon and declares a winner.
- **Interactive UI:** Displays Pokémon images, types, HP, and attack stats.
- **Background Music:** Includes battle music that plays when the fight starts.
- **Sound Effects:** Plays a short sound effect when the battle begins.
- **Animated UI:** Smooth animations for Pokémon cards and interactive elements.

## Technologies Used
- **HTML:** For structuring the web app.
- **CSS:** For styling and animations.
- **JavaScript:** For fetching Pokémon data, handling battles, and implementing audio features.
- **PokéAPI:** Used to retrieve Pokémon details.

## User Interface (UI)
The UI is designed to provide an engaging battle experience with animated elements and vibrant colors.

## The Logic Behind This Project
### Fetching Pokémon Data
The app uses the PokéAPI to retrieve random Pokémon data:
```javascript
function getPokemon(id) {
    return fetch(`https://pokeapi.co/api/v2/pokemon/${id}`)
        .then(response => response.json());
}
```

### Determining the Winner
The Pokémon with the higher attack stat wins the battle:
```javascript
function determineWinner(pokemon1, pokemon2) {
    let attack1 = pokemon1.stats[1].base_stat;
    let attack2 = pokemon2.stats[1].base_stat;
    
    return attack1 > attack2 ? pokemon1.name : attack2 > attack1 ? pokemon2.name : "Tie";
}
```

### Playing Background Music and Sound Effects
- **Background music:** Loops until manually paused.
- **Battle sound effect:** Plays for 4 seconds when the battle starts.
```javascript
var battleSound = new Audio('./battle-sound.mp3');
battleSound.play();
setTimeout(() => {
    battleSound.pause();
    battleSound.currentTime = 0;
}, 4000);
```

## Try out the Web App
[Try Demo Now](https://random-pokemon-battle-gold.vercel.app/)

## How to Use
1. Clone the repository:
```bash
git clone https://github.com/wazirkazimi/Random-Pokemon-Battl.git
```
2. Open the `index.html` file in your browser.
3. Click the **Battle!** button to fetch two random Pokémon.
4. View their details and see the battle result.

## Conclusion
The **Random Pokémon Battle Web App** is a fun and interactive project that utilizes APIs, JavaScript, and animations to create an engaging experience. Contributions and feedback are welcome!

