# Towers of Ivory - A Modern Text-Based Dungeon Crawler

Welcome to Towers of Ivory, a project developed by the students of the ASD class ITN-ASD-B 2024 at HAN University of Applied Sciences. This initiative is not only a technical endeavor but also an effort to connect the nostalgic value of classic text-based dungeon crawlers like Pedit5 and ADVENT with contemporary technological advancements.

## 🌟 Project Objective

The rise of games with advanced graphics has overshadowed the text-based dungeon crawler genre. There is a lack of modern games that capture and enrich the essence of classic dungeon crawlers using today’s technology, presenting a challenge for fans of the genre. HAN University has initiated this project with the vision to create a bridge between former generations and contemporary gamers.

Our aim is to rekindle interest in text-based dungeon crawlers by enhancing the genre with contemporary technologies, making the game continuously engaging and playable. The project is designed to attract a solid player base and breathe new life into the genre, with a special focus on multiplayer functionalities.

## 🎮 Features

- **Text-Based Interface**: Play in a complete ASCII world with no graphical user interface, making for a nostalgic yet fresh gaming experience.
- **Infinite World Generation**: No two play sessions have to be identical, thanks to a seed-based dynamic world generator that expands the game environment endlessly.
- **Multiplayer Capabilities**: Enjoy robust multiplayer options with real-time interaction via a peer-to-peer network that can be hosted on a local network.
- **Intelligent Software Agents**: Program your own agents with NLP-like configurations in a custom-developed language to play on your behalf, ensuring the game remains active and engaging, even in your absence.
- **Chat System**: Engage with other players through an in-game chat system, fostering a sense of community and camaraderie.

### Use Cases

A more in-detail description of the requirements is only available at request.

| Code   | Name                   | Brief description                                                                                              | Status |
|--------|------------------------|----------------------------------------------------------------------------------------------------------------|--------|
| UC1    | Create Game            | The player indicates wanting to start a new game. Preparation includes game type, name, game mode, agent config, seed. | Implemented |
| UC2    | Play Game              | The player can move their character through the world, pick up items, fight, and lose HP in battles.           | Implemented |
| UC2.1  | Move Game Character    | The player moves their character by choosing a direction, if the path is clear.                               | Implemented |
| UC2.2  | Perform Interaction    | The player can perform interactions such as attacking, picking up items, and entering stairs.                 | Implemented |
| UC2.2.1| Attack                 | The player attacks a character, loses HP based on DEF, gains XP and items upon defeating them.                | Implemented |
| UC2.2.2| Pick Up Item           | The player picks up an item.                                                                                   | Implemented |
| UC2.2.3| Enter Stairs           | The player enters stairs and goes to another floor.                                                           | Implemented |
| UC2.3  | Chat                   | The player communicates with other players via chat, with team or proximity settings.                         | Implemented |
| UC2.3.1| Send Team Chat Messages | The player sends messages to team members for strategy.                                                       | Implemented |
| UC2.3.2| Send Proximity Messages | The player sends messages to nearby players for strategy.                                                     | Not Implemented|
| UC3    | Configure Agent        | The player programs their software agent during game preparation.                                             | Implemented |
| UC4    | Join Game              | A player joins an ongoing game, replaces agent if previously participated.                                     | Implemented |
| UC5    | Leave Game             | The player stops temporarily, software agent takes over.                                                      | Implemented |
| UC6    | Enable Agent           | The player lets software agent play for them, can take over later.                                            | Partially Implemented |
| UC7    | Stop Game              | The game can be stopped without data loss, can be resumed later.                                              | Implemented |
| UC8    | Configure Game         | Configuration of game parameters to keep it interesting.                                                      | Not implemented |
| UC9    | Resume Game            | The player resumes the game from the last saved point.                                                        | In construction @Feature Branch Spel Hervatten |
| UC10   | Disable Agent          | The player takes back control after being replaced by software agent.                                         | Implemented |

### Functional Requirements

| code | description                                                                    | status |
|------|--------------------------------------------------------------------------------|--------|
| FR1  | Every passable tile is reachable.                                              | Implemented |
| FR2  | An agent of a player that left is runned on another client                     | Not Implemented |
| FR3  | Different types of terrain have different movement costs.                      | Not implemented |
| FR4  | Character interactions influence strengths and attributes.                     | Implemented |
| FR5  | A host is migrated in a game session after loss of connection with the host.   | In construction @Feature Branch Host Migration |
| FR6  | Every new game is played in a uniquely generated world.                        | Implemented |
| FR7  | The world must infinitely and dynamically generate new areas.                  | Implemented |
| FR8  | Players must be able to find each other's active game on the same network.     | Partially implemented |
| FR9  | There are monsters in rooms that can be fought.                                | Not implemented |
| FR10 | There is a Last Man Standing game mode.                                        | Partially Implemented |
| FR11 | There is a Capture the Flag game mode.                                         | Not implemented |
| FR13 | When there are 11 floors, the first floor is removed.                          | Implemented |
| FR14 | There is a Fog of War renderer available as an alternative world visualization.| Not Implemented |
| FR15 | There is a Field of View renderer available as an alternative world visualization.| Not Implemented |

## 🚧 Known Issues

The game is currently in full development. There are many problems that we are aware of and are working to resolve. Here are some of the biggest known issues:

### Network Issues on MacOS and Linux Systems

- **UDP Broadcast Handling**: Towers of Ivory utilizes UDP broadcast for network discovery of hosted games. MacOS and Linux systems are configured by default to ignore UDP packets, which limits these systems to only joining games that are hosted by others, rather than hosting games themselves.

### Game Desynchronization

- **State Synchronization**: There are instances where the game state among peers may desynchronize. This is due to the lack of a proper mechanism for synchronizing the game state across all players. Currently, the game does not check a hash of the current game state against the host's state and resend the game state to all peers when discrepancies are detected. This can lead to gameplay issues and inconsistencies.

### Issues with Seeds and Game State

- **Seed-Related Desynchronization**: Desynchronization may also occur in relation to certain game seeds, particularly when a player spawns next to an item. This issue is likely related to the current method of handling items within the game state, affecting the stability and consistency of the gameplay experience.

## 🤝 Contributing

We welcome contributions to make Towers of Ivory even better.
