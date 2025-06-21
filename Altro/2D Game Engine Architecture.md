___
## Moduli principali
### 1. `Core`
- **Application**: ciclo di vita dell'applicazione (`init`, `run`, `shutdown`)
- **Timer**: gestione `deltaTime` e frame rate
- **Logger**: log con livelli (`info`, `warning`, `error`)
- **Config**: parsing file di configurazione
- **Events**: input e altri eventi centralizzaati

### 2. `Graphics`
- **Renderer**: wrapper per `SDL_Renderer`
- **TextureManager**: caricamento/gestione delle immagini con `SDL_image`
- **Camera2D** viewport e scrolling
- **Sprite**: rendering e animazione 2D
- **FontRenderer**: testo su schermo con `SDL_ttf`

### 3. `Audio`
- **SoundManager**: gestione effetti sonori (`SDL_mixer`)
- **MusicManager**: gestione BGM e loop musicali

### 4. `Input`
- **InputManager**: tastiera, mouse, controller
- **Bindings**: configurazioni input da file (mappable)

### 5. `Network`
- **NetClient/NetServer**: networking TCP/UDP con `SDL_net`
- **PacketManager**: formattazione pacchetti binari e di stato

### 6. `ECS`
- **Entity**: ID numerico univoco
- **Component**: dati puri (`Position`, `Velocity`, `Sprite`, `Collider`)
- **System**: logica su gruppi di componenti (`PhysicsSystem`, `RenderSystem`)
- **Coordinator**: gestione entity/component/system

### 7. `Physics`
- **RigidBody2D**: massa, velocità, attrito, gravità.
- **Collider2D**: forme AABB, cerchi, poligoni
- **CollisionSystem**: rilevamento e risoluzione collisioni
- **PhysicsSystem**: integrazione e applicazione delle forze

### 8. `Scenes`
- **Scene**: astratta per menu, livelli, ecc.
- **SceneManager**: gestisce stack di scene e transizioni

### 9. `Scripting`
- `Lua` integrazione di scripting con `sol2`.
