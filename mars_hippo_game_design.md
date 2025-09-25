# MARS: Hippo Tycoon Game Design Document

## Game Overview

**MARS: Hippo Tycoon** evolves from a simple life simulator into a comprehensive zoo management and story-driven experience. Players nurture MARS, a rare pygmy hippo, through his life journey while building and managing a thriving wildlife park that celebrates hippo conservation.

---

## Core Progression System

### Sleep & Dream Mechanics

**Tiredness System:**
- New stat: **Energy** (0-100%, drains continuously)
- **Sleep threshold**: When energy drops below 20%, MARS becomes sluggish
- **Forced sleep**: At 0% energy, automatic sleep sequence triggers
- **Sleep benefits**: Restores energy, advances age, triggers story progression

**Dream Sequence Activation:**
```
Evening → Tiredness Check → Dream Animation → Story Progression → New Day
```

### The Four Dream Sequences

Each dream represents a major life milestone, triggered by age and story progression:

---

## MARS's Story Arc

### Background
MARS is a male pygmy hippo born June 26, 2025, at Tanganyika Wildlife Park. As one of only ~2,500 pygmy hippos remaining in the wild, his birth represents hope for the species. His journey from internet sensation to conservation ambassador forms the heart of our narrative.

### Dream Sequence 1: "The Famous Pool Incident" 
**Age Trigger:** 30 days old
**Story Context:** MARS's viral moment

> **Dream Bubble 1:** *"I was just a tiny hippo who loved the water..."*
> **Dream Bubble 2:** *"Mom gave me THAT look when I wouldn't get out..."*
> **Dream Bubble 3:** *"Suddenly, millions of people knew my name!"*
> **Dream Bubble 4:** *"I became famous for being stubborn... just like a real hippo!"*

**Progression:** MARS grows to Juvenile size, habitat gains first visitors

### Dream Sequence 2: "Learning to Be Wild"
**Age Trigger:** 180 days old  
**Story Context:** Developing natural behaviors

> **Dream Bubble 1:** *"Dad taught me how real hippos live in the wild..."*
> **Dream Bubble 2:** *"Rivers in Liberia where my ancestors swam freely..."*
> **Dream Bubble 3:** *"I'm not just cute - I'm part of something bigger!"*
> **Dream Bubble 4:** *"Every day I grow stronger, wilder, prouder..."*

**Progression:** MARS grows to Adolescent, unlocks new behavioral patterns, habitat expands

### Dream Sequence 3: "The Conservation Mission"
**Age Trigger:** 1 year old
**Story Context:** Understanding his role in species survival

> **Dream Bubble 1:** *"Scientists came to study me, to learn about my kind..."*
> **Dream Bubble 2:** *"Only 2,500 of us left in all the world..."*
> **Dream Bubble 3:** *"But I'm helping people care, helping them understand..."*
> **Dream Bubble 4:** *"My story gives hope to hippos everywhere!"*

**Progression:** MARS grows to Young Adult, educational programs unlock, research facilities available

### Dream Sequence 4: "Legacy of Hope"
**Age Trigger:** 2 years old
**Story Context:** Becoming a symbol of conservation

> **Dream Bubble 1:** *"Children visit from schools around the world..."*
> **Dream Bubble 2:** *"They learn that every creature matters..."*
> **Dream Bubble 3:** *"My fame helps protect my wild cousins..."*
> **Dream Bubble 4:** *"I may be small, but my impact is mighty!"*

**Progression:** MARS reaches Adult size, breeding program unlocks, maximum zoo features available

---

## Zoo Visitor System

### Crowd Mechanics
**Visitor Types:**
- **School Groups**: Educational focus, higher learning impact
- **Families**: Entertainment focus, longer stays, snack purchases
- **Researchers**: Conservation focus, generate research points
- **Tourists**: Photo opportunities, social media promotion
- **VIP Donors**: Major funding, special event requirements

**Visitor Behaviors:**
- **Path-finding** to different zoo attractions
- **Feeding time gatherings** around MARS's habitat
- **Photo opportunities** at designated viewpoints
- **Educational interactions** at information kiosks
- **Gift shop visits** and souvenir purchases

### Entertainment Infrastructure

**Essential Attractions:**
- **Viewing Platforms**: Elevated walkways for optimal sightlines
- **Feeding Stations**: Scheduled feeding shows with educational commentary
- **Photo Booths**: MARS-themed background scenes
- **Information Kiosks**: Interactive displays about pygmy hippos
- **Playground Area**: Hippo-themed play structures for children

**Advanced Features:**
- **Amphitheater**: Educational presentations and conservation talks
- **Research Center**: Visible science in action
- **Gift Shop**: MARS merchandise and conservation donations
- **Café**: Hippo-themed dining with habitat views
- **VIP Viewing Area**: Premium experience for major donors

---

## Economic Systems

### Revenue Streams
1. **Admission Fees**: Base income from visitor entry
2. **Concessions**: Food, drinks, souvenirs
3. **Educational Programs**: School group bookings, camps
4. **Research Grants**: Conservation research funding
5. **Donations**: Visitor contributions to hippo conservation
6. **Merchandise**: MARS-branded items and memorabilia

### Resource Management
- **Staff Hiring**: Zookeepers, educators, researchers, maintenance
- **Facility Upgrades**: Habitat improvements, visitor amenities
- **Conservation Programs**: Wildlife protection initiatives
- **Marketing Campaigns**: Increasing visitor awareness and attendance

### Progression Unlocks
- **Reputation System**: Fame unlocks new opportunities
- **Conservation Impact**: Success enables expansion to other species
- **Research Milestones**: Scientific breakthroughs provide bonuses
- **Community Engagement**: Local support increases funding

---

## Technical Implementation Roadmap

### Phase 1: Sleep & Story System
**User Story 1.1**: Tiredness Mechanic
```
As a player, I want MARS to get tired over time so that natural sleep cycles create story progression opportunities.

Acceptance Criteria:
- Energy stat decreases continuously based on activity level
- Visual indicators show MARS becoming sluggish when tired
- Automatic sleep triggers at 0% energy
- Sleep restores energy and advances story timeline
```

**User Story 1.2**: Dream Sequence Framework
```
As a player, I want to experience MARS's dreams as story sequences so that I understand his character development and life journey.

Acceptance Criteria:
- Four distinct dream animations with story bubbles
- Age-based triggering system
- Smooth transitions between gameplay and story modes
- Story progress saves and persists between sessions
```

### Phase 2: Visitor System
**User Story 2.1**: Basic Crowd Simulation
```
As a player, I want to see visitors coming to see MARS so that the habitat feels like a real zoo environment.

Acceptance Criteria:
- Visitors spawn at habitat entrance and move along paths
- Different visitor types with unique behaviors and appearances
- Visitors react to MARS's activities and feeding times
- Visitor satisfaction affects zoo reputation and revenue
```

**User Story 2.2**: Entertainment Infrastructure
```
As a player, I want to build attractions for visitors so that I can increase zoo popularity and revenue.

Acceptance Criteria:
- Viewing platforms, photo booths, and information kiosks
- Construction system with costs and placement restrictions
- Visitor usage affects attraction effectiveness and wear
- Upgrades improve visitor satisfaction and spending
```

### Phase 3: Economic System
**User Story 3.1**: Revenue Generation
```
As a player, I want to earn money from visitors so that I can expand and improve the zoo facilities.

Acceptance Criteria:
- Multiple revenue streams (admission, concessions, donations)
- Dynamic pricing based on MARS's fame and visitor demand
- Financial dashboard showing income, expenses, and profit
- Budget constraints that require strategic spending decisions
```

**User Story 3.2**: Staff Management
```
As a player, I want to hire and manage zoo staff so that operations run smoothly and visitors have a quality experience.

Acceptance Criteria:
- Different staff types (keepers, educators, maintenance)
- Staff performance affects habitat cleanliness and visitor satisfaction
- Training and promotion systems for staff development
- Labor costs balanced against operational benefits
```

### Phase 4: Advanced Features
**User Story 4.1**: Research & Conservation
```
As a player, I want to support hippo research and conservation so that MARS's story contributes to real-world impact.

Acceptance Criteria:
- Research projects that unlock new knowledge and abilities
- Conservation campaigns that increase public awareness
- Partnerships with real conservation organizations
- Impact metrics showing player contribution to species protection
```

**User Story 4.2**: Breeding Program
```
As a player, I want to eventually participate in hippo breeding programs so that MARS can help ensure his species' survival.

Acceptance Criteria:
- Adult MARS can participate in species survival plan
- Mate selection based on genetic compatibility
- Breeding success affects conservation reputation
- Educational content about responsible breeding practices
```

---

## Development Prompts for Senior JavaScript Engineer

### Core Systems Implementation

**Prompt 1: Sleep System Architecture**
```
Implement a comprehensive sleep system for MARS including:
- Energy stat that decreases over time based on activity levels
- Visual fatigue indicators (slower movement, drooping animations)
- Automatic sleep sequence triggering at energy thresholds
- Day/night cycle progression during sleep
- Dream sequence state management with story progression tracking
- Energy restoration calculation based on sleep quality and duration
```

**Prompt 2: Story Sequence Engine**
```
Build a flexible story sequence system that handles:
- Modal overlay system for dream sequences
- Text bubble animations with typewriter effects
- Background animation during dreams (floating, ethereal effects)
- Story progression state management with save/load functionality
- Age-based trigger system for different story milestones
- Smooth transitions between gameplay and story modes
- Story completion rewards and character progression
```

**Prompt 3: Visitor Crowd Simulation**
```
Create a visitor management system featuring:
- Pathfinding system for multiple visitor types moving through zoo
- Visitor spawning with weighted probability for different demographics
- Attraction interest calculation based on visitor type and current activities
- Queue management for popular attractions and feeding times
- Visitor satisfaction metrics affecting spending and word-of-mouth
- Performance optimization for handling 50+ concurrent visitors
```

**Prompt 4: Economic Engine**
```
Develop a comprehensive economic system including:
- Multiple revenue stream tracking (admissions, concessions, donations)
- Dynamic pricing algorithms based on reputation and demand
- Expense management for staff, maintenance, and facility upgrades
- Budget planning tools and financial forecasting
- Investment return calculations for attraction and habitat improvements
- Economic crisis events and recovery mechanisms
```

### Advanced Features

**Prompt 5: Construction & Upgrade System**
```
Build a zoo construction management system with:
- Grid-based placement system for buildings and attractions
- Resource requirements and construction time mechanics
- Upgrade paths for existing facilities with cost-benefit analysis
- Visitor flow optimization through facility placement
- Environmental impact considerations for habitat modifications
- Construction project queue management and prioritization
```

**Prompt 6: Staff AI & Management**
```
Implement intelligent staff management featuring:
- AI staff members with specific roles and performance metrics
- Automated task assignment based on priority and staff availability
- Training programs that improve staff effectiveness over time
- Staff satisfaction and retention mechanics
- Performance review system with hiring/firing decisions
- Union negotiations and workplace condition requirements
```

**Prompt 7: Research & Conservation Systems**
```
Create educational and conservation game mechanics:
- Research project management with real-world hippo conservation data
- Educational program development affecting visitor learning outcomes
- Partnership system with conservation organizations
- Impact measurement dashboard showing real-world conservation contributions
- Grant application mini-game for funding conservation initiatives
- Public awareness campaigns with social media integration
```

**Prompt 8: Save System & Analytics**
```
Develop comprehensive data management including:
- Robust save/load system supporting complex game state
- Player analytics tracking engagement, progression, and retention
- Achievement system with conservation-focused milestones
- Leaderboard integration for zoo success metrics
- Export functionality for sharing zoo designs and MARS stories
- Cloud save synchronization across devices
```

---

## Success Metrics

### Player Engagement
- **Daily Active Users**: Consistent player return rate
- **Session Duration**: Average time spent nurturing MARS and managing zoo
- **Story Completion Rate**: Percentage of players experiencing all dream sequences
- **Conservation Learning**: Educational impact measurement through quiz performance

### Economic Indicators
- **Zoo Profitability**: Player success in managing sustainable operations
- **Visitor Satisfaction**: Quality of experience provided to zoo guests
- **Conservation Contribution**: In-game donations to real hippo conservation efforts
- **Research Impact**: Scientific knowledge unlocked through gameplay

### Technical Performance
- **Load Times**: Fast startup and smooth transitions between game modes
- **Scalability**: Support for increasing complexity as zoos expand
- **Cross-Platform**: Consistent experience across web, mobile, and desktop
- **Data Integrity**: Reliable save/load functionality with minimal loss

---

This comprehensive design transforms MARS from a simple life simulator into an engaging educational experience that combines entertainment with meaningful conservation awareness, creating a sustainable gameplay loop that grows more complex and rewarding as players progress through MARS's life journey.