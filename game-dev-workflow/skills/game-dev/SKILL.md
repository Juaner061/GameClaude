---
name: game-dev
description: Game development workflow skill for solo/small team game development with AI. Covers preproduction, vertical slice, content expansion, and polish phases using specialized game agents.
---

# Game Development Workflow Skill

## Overview

Execute game development workflow for solo/small team developers using AI-powered agents. This workflow covers the complete game development lifecycle from creative vision to release-ready build, with specialized agents for each discipline.

## When to Use

- Starting a new game project from a concept
- Need to design gameplay systems and mechanics
- Creating technical specifications for Unity implementation
- Designing progression, economy, and meta-game systems
- Building content pipelines for art integration
- Planning vertical slice or content expansion
- Preparing game for release

## Usage

### Phase 1: Preproduction (Recommended Starting Point)

```bash
/game-dev "开始前期制作：[游戏概念]" --phase preproduction
```

**Example:**
```bash
/game-dev "一个2D挂机RPG游戏，玩家在大地图上探索、打怪、收集装备" --phase preproduction
```

**This phase executes:**
1. Creative Director agent - Define game vision, player fantasy, experience pillars
2. Gameplay Designer agent - Design core gameplay loop, player actions, combat flow
3. System Designer agent - Design progression, economy, meta-game systems
4. Technical Designer agent - Create Unity technical specifications

**Output:** `./.claude/game/{game_name}/`
- `00-creative-vision.md` - Creative foundation
- `01-gameplay-design.md` - Core gameplay rules
- `02-systems-design.md` - Progression and systems
- `03-technical-spec.md` - Unity implementation plan

### Phase 2: Vertical Slice Development

```bash
/game-dev "开始垂直切片开发" --phase vertical-slice
```

**This phase executes:**
1. Technical Designer agent - Implement core systems architecture
2. Content Pipeline Designer agent - Set up asset workflow and prefab templates
3. Level Content Designer agent - Create playable prototype level
4. AI Producer agent - Coordinate integration and playtesting

**Output:** Playable prototype demonstrating core gameplay loop (2-5 minutes)

### Phase 3: Content Expansion

```bash
/game-dev "扩展游戏内容：[扩展目标]" --phase content-expansion
```

**Example:**
```bash
/game-dev "添加10个新关卡、5种新敌人、完整装备系统" --phase content-expansion
```

**This phase executes:**
1. System Designer agent - Implement full progression systems
2. Level Content Designer agent - Create levels, enemies, items
3. Technical Designer agent - Integrate new systems and content
4. AI Producer agent - Balance tuning and integration verification

**Output:** Complete game with all content, playable from start to finish

### Phase 4: Polish & Release

```bash
/game-dev "游戏打磨：[打磨重点]" --phase polish
```

**Example:**
```bash
/game-dev "优化UI、提升性能、修复所有critical bug" --phase polish
```

**This phase executes:**
1. Technical Designer agent - Performance optimization and critical bug fixes
2. AI Producer agent - Quality assurance and release preparation
3. All agents - Collaborative polish based on focus area

**Output:** Release-ready build, submission materials prepared

## Options

- `--phase <phase>`: Specify development phase
  - `preproduction`: Initial design and planning (default for new projects)
  - `vertical-slice`: Build first playable prototype
  - `content-expansion`: Scale content and systems
  - `polish`: Final refinement and optimization

- `--target-platform <platform>`: Target platform (default: Unity 2D)
- `--focus-area <area>`: Specific focus for polish phase (ui, performance, art, audio, balance, all)

## Game Development Agents

### 1. Creative Director
- **Role**: Define game vision, player fantasy, experience pillars
- **Input**: Game concept, target audience, platform constraints
- **Output**: Creative vision document with non-goals

### 2. Gameplay Designer
- **Role**: Design core gameplay loop, player actions, combat/exploration flow
- **Input**: Creative vision from Creative Director
- **Output**: Gameplay rules and mechanics specification

### 3. System Designer
- **Role**: Design progression systems, economy, meta-game loops
- **Input**: Gameplay design and creative vision
- **Output**: System architecture with balance considerations

### 4. Technical Designer
- **Role**: Create Unity technical specifications, architecture, data structures
- **Input**: All upstream designs (creative, gameplay, systems)
- **Output**: Implementation-ready technical specifications

### 5. Content Pipeline Designer
- **Role**: Design art asset pipeline, prefab templates, workflow
- **Input**: Technical specifications and creative vision
- **Output**: Asset workflow documentation and templates

### 6. Level Content Designer
- **Role**: Create actual game content (levels, enemies, items, missions)
- **Input**: Gameplay rules, system design, content pipeline
- **Output**: Playable game content configurations

### 7. AI Producer
- **Role**: Coordinate all agents, manage integration, quality assurance
- **Input**: All agent outputs and project state
- **Output**: Integration reports, release checklist

## Workflow Quality Gates

Each phase has mandatory quality thresholds:

- **Preproduction**: ≥90% design quality before approval
- **Vertical Slice**: ≥90% quality before content expansion
- **Content Expansion**: ≥85% quality before polish
- **Polish**: ≥95% quality before release

**User approval gates** at critical points ensure you maintain control over the development direction.

## Typical Workflow Sequence

```
1. /game-dev "游戏概念" --phase preproduction
   → Design documents created
   → Review and approve

2. /game-dev "开始垂直切片" --phase vertical-slice
   → Playable prototype created
   → Test and refine

3. /game-dev "扩展内容目标" --phase content-expansion
   → Full game built
   → Balance and integrate

4. /game-dev "打磨重点" --phase polish
   → Release-ready build
   → Submit to platform
```

## Output Directory Structure

```
./.claude/game/{game_name}/
├── 00-creative-vision.md           # Creative foundation
├── 01-gameplay-design.md           # Core gameplay rules
├── 02-systems-design.md            # Progression systems
├── 03-technical-spec.md            # Unity implementation
├── 04-vertical-slice-plan.md      # Vertical slice plan
├── 05-vertical-slice-report.md    # Prototype results
├── 06-expansion-plan.md            # Content roadmap
├── 07-content-expansion-report.md # Expansion results
├── 08-polish-plan.md               # Polish roadmap
├── 09-release-report.md            # Final report
└── 10-release-checklist.md         # Submission checklist
```

## Best Practices

1. **Start with Preproduction**: Always begin with `/game-dev --phase preproduction` for new projects
2. **Review Each Phase**: Carefully review outputs before proceeding
3. **Iterate if Needed**: Don't hesitate to refine designs in current phase
4. **Follow Agent Chain**: Each agent builds on previous outputs
5. **Quality Over Speed**: Ensure 90% quality threshold before moving forward
6. **Unity 2D Default**: Assumes Unity 2D unless specified otherwise
7. **Solo/Small Team**: Optimized for 1-5 person teams

## Language Support

- Input language matches output language
- Chinese input → Chinese documentation
- English input → English documentation
- Technical terms remain in English (Unity, ScriptableObject, etc.)

## Integration with Claude Code

This skill works seamlessly with Claude Code's workflow system. Agents are invoked as sub-agents with proper context passing and output collection.

## Example Session

```bash
# Start with game concept
User: /game-dev "一个像素风的放置类RPG，玩家挂机战斗、收集装备、逐步解锁新地图"

# Claude executes preproduction phase:
- Creative Director: Defines retro fantasy adventure pillars
- Gameplay Designer: Designs idle combat loop and progression
- System Designer: Creates equipment tiers and unlock system
- Technical Designer: Specifies Unity 2D pixel art architecture

# Review outputs, then proceed
User: /game-dev "开始做垂直切片" --phase vertical-slice

# Claude builds prototype with core gameplay
User: /game-dev "添加5个新地图、20种装备、BOSS战" --phase content-expansion

# Claude expands content
User: /game-dev "优化性能、打磨UI" --phase polish

# Claude prepares release build
```

## Common Use Cases

**New Game Project:**
```bash
/game-dev "一个2D平台跳跃游戏，类似Celeste但更简单，适合移动端" --phase preproduction
```

**Add Gameplay Systems:**
```bash
/game-dev "设计技能系统和天赋树" --phase content-expansion
```

**Optimize Performance:**
```bash
/game-dev "优化帧率到60FPS，减少加载时间" --phase polish --focus-area performance
```

**Design Economy:**
```bash
/game-dev "设计金币经济和商店系统" --phase content-expansion
```

## Quality Checklist

Before moving to next phase, verify:
- [ ] All design documents complete and clear
- [ ] Technical specifications implementable
- [ ] Agent outputs consistent with each other
- [ ] Quality score ≥90% (preproduction, vertical slice)
- [ ] Quality score ≥85% (content expansion)
- [ ] Quality score ≥95% (polish)
- [ ] User approval obtained at approval gates

---

**Remember**: This workflow is designed for solo/small team game development with AI assistance. Each agent has specialized expertise, and the workflow ensures systematic progress from concept to release.
