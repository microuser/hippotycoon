# hippotycoon
MARS the Hippo living large in a zoo life simulator

## MARS Baby Hippo Simulator 

A rich interactive ecosystem simulation featuring MARS, the famous baby hippo from Tanganyika Wildlife Park. Experience autonomous AI behavior, skill-based scoring, and complex creature interactions in MARS's dynamic habitat.

## Core Features

###  Autonomous AI System
- **Intelligent Decision Making**: MARS evaluates her needs and makes autonomous choices
- **Priority-Based Actions**: Urgent needs (>50%) override normal behavior patterns
- **Action Queue Visualization**: Watch MARS's thought process in real-time
- **Manual Override**: Left-click to guide MARS when needed

###  Interactive Gameplay
- **Backflip Combos**: Press Space in water for spectacular +10,000 point backflips
- **Scoring System**: Track achievements and skill-based performance
- **Rock Interactions**: Right-click rocks to spawn beetles, nudge rocks while hunting
- **Enhanced Controls**: Comprehensive input system with visual feedback

###  Living Ecosystem
- **Dynamic Beetle Behavior**: Beetles swarm, scatter, hide, and are attracted to poop
- **Frog Hunting**: Chase tasty frogs that spawn from water and hide under rocks
- **Progressive Poop System**: Waste accumulates in realistic growing piles
- **Boundary Management**: All creatures stay within the habitat fence

###  Advanced Life Simulation
- **Progressive Happiness Drain**: Earlier penalties for bladder/bowel (>30%) and hunger (>40%)
- **Enhanced Nutrition**: Frogs provide superior nourishment compared to beetles
- **Growth Tracking**: Watch MARS develop through life stages
- **Day/Night Cycle**: Dynamic lighting and sleep patterns

## Enhanced Controls

### Keyboard Controls
- **Space Bar**: Perform backflip combo (when in water) - +10,000 points!

### Mouse Controls
- **Left Click**: Manual movement override with visual target indicator
- **Right Click**: Rock interaction (spawn beetles, must be within range)

### UI Controls
- **Time Speed**: Cycle through 1x, 5x, 10x game speeds
- **Sleep Button**: Manual sleep (available at night or when exhausted)
- **Splash Button**: Manual splash action (only when in water)
- **Journal**: Multi-tab interface with story,missions, logs, and character info
- **Save/Load**: Complete game state persistence

## Creature Behaviors

###  Beetle Ecosystem
- **Attraction**: Beetles love to skurry toward poop piles
- **Swarming**: Every ~10 seconds, beetles swarm around poop then scatter to hide
- **Hiding**: Beetles hide under rocks or other poop piles after swarming
- **Rock Nudging**: MARS can nudge rocks while hunting to spawn fleeing beetles
- **Boundary Respect**: All beetles stay within habitat and drift back toward center

###  Frog System
- **Water Spawning**: Up to 4 frogs spawn from pools and hop around habitat
- **Hiding Behavior**: Frogs can hide under rocks, especially when at population cap
- **Distance-Based Hiding**: Farthest frog from MARS hides when at maximum count
- **Enhanced Nutrition**: Frogs provide better hunger relief and happiness boost

###  Rock Mechanics
- **Interactive Turning**: Right-click to turn rocks and spawn beetles
- **Auto-Reset**: Rocks return to normal after ~20 seconds with smooth animation
- **Nudge Spawning**: MARS nudges rocks during hunting to create fleeing beetles
- **No Relocation**: Rocks stay in place when resetting (improved from original)

## Visual & Audio Feedback

###  Special Effects
- **Backflip Sequence**: Camera shake, water splash, vapor mist, Congratulations message
- **2x Zoom**: Enhanced camera view for closer gameplay
- **Smooth Animations**: Rock rotation, creature movement, environmental transitions
- **Particle Systems**: Water splash, vapor effects, visual polish

###  User Interface
- **Action Logging**: All manual actions logged to message panel
- **Real-time Stats**: Live updates of all life statistics
- **Score Display**: Persistent score tracking in stats panel
- **AI Status**: Current action and reasoning display
- **Boundary Feedback**: Visual indicators for habitat limits

## Technical Architecture

### Game Loop Structure
```
Main Loop:
├── AI Decision Making (evaluateNeeds, updateMarsAI)
├── Physics & Movement (updateMars, boundary enforcement)
├── Creature Management (updateBeetles, updateFrogs)
├── Life Simulation (updateStats, progressive happiness)
├── Environmental Systems (day/night, updateEnvironment)
├── Special Actions (updateBackflip, animateSplash)
└── UI Updates (scoring, action logging, status display)
```

### Data Flow
- **Input Events** → Manual overrides and special actions
- **AI Evaluation** → Autonomous behavior and target selection  
- **Physics Systems** → Movement, gravity, boundary enforcement
- **Creature Interactions** → Spawning, eating, hiding behaviors
- **State Management** → Stats progression, scoring, persistence

## Conservation & Educational Value

MARS became famous for her adorable pool stubbornness, but this enhanced simulation teaches:
- **Ecosystem Complexity**: Understanding predator-prey relationships
- **Habitat Management**: Importance of environmental boundaries
- **Species Behavior**: Realistic animal decision-making patterns
- **Conservation Awareness**: Pygmy hippos have only ~2,500 individuals remaining

## Getting Started

1. **Observe**: Monitor MARS's autonomous decision-making in the action queue
2. **Interact**: Try the backflip combo (Space in water) for high scores
3. **Explore**: Watch the creature ecosystem develop with beetles and frogs
4. **Guide**: Use manual overrides when needed, but let MARS be autonomous
5. **Progress**: Track growth, scoring, and story development through the journal

Experience the most advanced hippo life simulation with realistic AI, complex ecosystems, and engaging skill-based gameplay!
