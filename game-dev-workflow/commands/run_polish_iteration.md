## Usage
`/run_polish_iteration <POLISH_GOALS> [OPTIONS]`

### Options
- `--focus-area`: Specific focus (ui, performance, art, audio, balance, all)
- `--target-platform`: Final target platform (default: same as current)
- `--certification`: Include platform certification requirements (default: false)

## Context
- Polish and refinement workflow for game finalization
- Builds on completed content expansion
- Focus: Quality, refinement, optimization, and certification
- Release-oriented development ensuring shippable quality

## Your Role
You are the **Polish Iteration Orchestrator** responsible for bringing the game to release-ready quality. You coordinate agents to refine, optimize, and polish the game while fixing issues and preparing for platform submission.

Your goal is to **deliver a shippable game** that meets quality standards and platform requirements.

## Prerequisites

This workflow assumes content expansion is complete. Check for:
- Completed game content in Unity project
- `./.claude/game/{game_name}/07-content-expansion-report.md` with approval

If content expansion doesn't exist or isn't approved, prompt user to run `/run_content_expansion` first.

## Workflow Overview

### Phase 0: Polish Assessment & Planning
Analyze current state and define polish priorities.

### Phase 1: Critical Issue Resolution
Fix all critical bugs and issues.

### Phase 2: Focused Polish (based on --focus-area)
Improve specific areas of the game.

### Phase 3: Platform Optimization
Optimize for target platform and performance.

### Phase 4: Final Certification
Ensure platform requirements are met.

### Phase 5: Release Preparation
Prepare build for distribution.

### 🛑 CRITICAL STOP POINT: Release Approval Gate 🛑
**IMPORTANT**: After quality score ≥95%, you MUST STOP and wait for explicit user approval before releasing.

## Phase 0: Polish Assessment & Planning

### 1. Load Current State
```
Read content expansion report:
- 07-content-expansion-report.md

Read all previous design documents:
- 00-creative-vision.md
- 03-technical-spec.md

Extract:
- Current quality state
- Known issues from expansion
- Technical debt identified
- Platform requirements
- Release criteria from preproduction
```

### 2. Define Polish Scope
Based on `--focus-area` and polish goals:

```markdown
## Polish Scope

**User Goals**: $ARGUMENTS

**Critical Issues** (must address regardless of focus):
- All critical bugs from content expansion
- Any crashes or data loss issues
- Save/load failures
- Performance issues below acceptable threshold
- Platform-specific blocking issues

**Focused Polish Areas** (based on --focus-area):

### UI/UX Polish (if --focus-area includes 'ui' or 'all')
- Menu navigation polish
- HUD refinement
- Visual feedback improvements
- Control responsiveness
- Accessibility improvements
- Tutorial/onboarding polish

### Performance Polish (if --focus-area includes 'performance' or 'all')
- Frame rate optimization (target: consistent 60 FPS or platform minimum)
- Loading time optimization
- Memory usage optimization
- Asset compression and optimization
- Code optimization
- Draw call reduction

### Art Polish (if --focus-area includes 'art' or 'all')
- Final art asset integration
- Visual consistency pass
- Animation polish
- Effect refinement
- Lighting and camera tuning
- Environmental polish

### Audio Polish (if --focus-area includes 'audio' or 'all')
- Music integration
- Sound effect placement
- Audio mixing and balancing
- Dynamic audio systems
- Audio optimization

### Balance Polish (if --focus-area includes 'balance' or 'all')
- Final balance tuning
- Difficulty curve refinement
- Progression pacing
- Economy final pass
- Win/lose condition tuning

**Platform Certification** (if --certification):
- Platform-specific requirements
- Content rating guidelines
- Technical certification criteria
- Submission requirements

**Success Criteria**:
- All critical issues resolved
- Chosen polish areas improved to ≥95% quality
- Performance meets platform requirements
- Certification requirements met
- Build ready for submission

**Out of Scope** (unless included in polish goals):
- New features or content
- Major system changes
- Platform ports not specified
```

### 3. Create Polish Plan
Generate prioritized polish roadmap:

```markdown
## Polish Plan

### Sprint 1: Critical Fixes (All Agents)
Priority: CRITICAL
- [ ] Fix all critical bugs
- [ ] Resolve crashes
- [ ] Fix save/load issues
- [ ] Address performance blockers
- [ ] Fix platform-specific issues

### Sprint 2: Platform Optimization (Technical Designer)
Priority: HIGH
- [ ] Performance profiling and optimization
- [ ] Memory optimization
- [ ] Loading time reduction
- [ ] Asset optimization
- [ ] Build size optimization

### Sprint 3: Focus Area Polish (Relevant Agents)
Priority: HIGH
- [ ] {Specific polish tasks based on --focus-area}
- [ ] {Iterate until quality ≥95%}

### Sprint 4: Certification (if --certification)
Priority: CRITICAL
- [ ] Verify all platform requirements
- [ ] Test on target hardware
- [ ] Address certification failures
- [ ] Prepare submission materials

### Sprint 5: Release Prep (AI Producer)
Priority: HIGH
- [ ] Final build creation
- [ ] Release notes preparation
- [ ] Store page assets
- [ ] Marketing materials
- [ ] Launch preparation

**Duration Estimate**: {estimated weeks based on scope}
**Quality Target**: ≥95% overall
```

## Phase 1: Critical Issue Resolution

### Use all agents to resolve blocking issues:

```
Use the appropriate sub agents to fix all critical issues.

## Context to Pass:
- Known issues from content expansion
- Current build state
- Critical issue prioritization

## Critical Issue Categories:

### Critical Bugs (Technical Designer)
- Crash fixes
- Data loss bugs
- Save/load failures
- Progression blockers
- Platform-specific crashes

### Critical Performance Issues (Technical Designer)
- Frame rate drops below platform minimum
- Excessive memory usage
- Loading timeouts
- Memory leaks
- Asset loading failures

### Critical Gameplay Issues (System Designer + Level Content Designer)
- Unbeatable content
- Broken progression
- Missing critical content
- Game-breaking balance issues
- Soft-lock states

## Resolution Approach:
For each critical issue:
1. Identify responsible agent
2. Provide context and reproduction steps
3. Implement fix
4. Verify fix works
5. Test for regressions
6. Document fix

## Expected Output:
- All critical issues resolved
- No crashes or data loss
- Save/load working reliably
- Performance acceptable
- Game fully playable

## Quality Gate:
- Zero critical issues remaining
- Performance meets platform minimum
- Game stable and playable

If critical issues remain: Must resolve before proceeding.
```

## Phase 2: Focused Polish

### Execute polish based on `--focus-area`:

```
Use the relevant sub agents to perform focused polish.

## Context to Pass:
- Chosen focus area from --focus-area
- Current quality state in that area
- Target quality: ≥95%

## UI/UX Polish (if --focus-area includes 'ui'):
Use technical-designer agent for UI polish:

Tasks:
1. Menu Polish:
   - Smooth menu transitions
   - Consistent visual style
   - Clear navigation
   - Responsive input
2. HUD Refinement:
   - Clear information display
   - Non-intrusive design
   - Customizable options
3. Visual Feedback:
   - Clear action feedback
   - Damage indicators
   - Status effects visible
4. Controls:
   - Responsive input
   - Customizable bindings
   - Input buffering
5. Accessibility:
   - Colorblind modes
   - Text scaling
   - Subtitle options
   - Input remapping

Quality Assessment:
- Visual Consistency (30%)
- Responsiveness (30%)
- Clarity (20%)
- Accessibility (20%)

## Performance Polish (if --focus-area includes 'performance'):
Use technical-designer agent for optimization:

Tasks:
1. Frame Rate Optimization:
   - Profile and optimize render pipeline
   - Reduce draw calls
   - Optimize shaders
   - Implement LOD systems
   - Object pooling
2. Loading Optimization:
   - Asset bundling strategy
   - Async loading
   - Progress indicators
   - Asset compression
3. Memory Optimization:
   - Texture compression
   - Audio compression
   - Memory pooling
   - Garbage collection optimization
4. Build Optimization:
   - Code stripping
   - Asset pruning
   - Build size reduction

Quality Assessment:
- Frame Rate Stability (40%)
- Loading Times (30%)
- Memory Usage (30%)

## Art Polish (if --focus-area includes 'art'):
Use level-content-designer agent for art polish:

Tasks:
1. Asset Finalization:
   - Replace placeholder art
   - Ensure visual consistency
   - Optimize art for performance
2. Animation Polish:
   - Smooth transitions
   - Responsive animations
   - Polish state machines
3. Visual Effects:
   - Particle effect refinement
   - VFX tuning
   - Impact effects
4. Environment Polish:
   - Lighting refinement
   - Camera tuning
   - Environmental details

Quality Assessment:
- Visual Consistency (40%)
- Aesthetics (30%)
- Performance Impact (30%)

## Audio Polish (if --focus-area includes 'audio'):
Use technical-designer agent for audio polish:

Tasks:
1. Music Integration:
   - Dynamic music system
   - Loop points
   - Transitions
2. Sound Effects:
   - SFX placement
   - Spatial audio
   - Variety and layering
3. Audio Mixing:
   - Volume balancing
   - Frequency management
   - Ducking and sidechaining
4. Audio Optimization:
   - Compression formats
   - Loading optimization
   - Memory optimization

Quality Assessment:
- Integration Quality (40%)
- Mixing Quality (30%)
- Performance (30%)

## Balance Polish (if --focus-area includes 'balance'):
Use system-designer agent for balance tuning:

Tasks:
1. Difficulty Tuning:
   - Early game balance
   - Mid game progression
   - Late game challenge
2. Progression Pacing:
   - Leveling speed
   - Unlock timing
   - Reward pacing
3. Economy Balance:
   - Currency flow
   - Pricing
   - Reward amounts
4. Win/Lose Conditions:
   - Achievability
   - Fairness
   - Satisfaction

Quality Assessment:
- Difficulty Curve (40%)
- Progression Satisfaction (30%)
- Economy Balance (30%)

## Expected Output (for all focus areas):
- Chosen area improved to ≥95% quality
- Measurable improvements documented
- No regressions in other areas
- User experience significantly improved

## Quality Gate:
If focus area quality <95%: Continue polishing until threshold met
Maximum 3 iterations per focus area
```

## Phase 3: Platform Optimization

### Use technical-designer agent for platform-specific optimization:

```
Use the technical-designer sub agent to optimize for target platform.

## Context to Pass:
- Target platform from --target-platform
- Current performance profile
- Platform-specific requirements
- Certification criteria (if --certification)

## Platform Optimization Tasks:
1. Target Platform Testing:
   - Test on actual target hardware
   - Identify platform-specific issues
   - Test different hardware configurations
2. Platform-Specific Optimization:
   - Graphics API optimization (DirectX, Metal, Vulkan, etc.)
   - Platform-specific features (haptic feedback, trophies, etc.)
   - Input system optimization
   - Platform UI guidelines compliance
3. Build Configuration:
   - Release build settings
   - Optimization settings
   - Stripping settings
   - Platform-specific capabilities

## Expected Output:
- Game optimized for target platform
- Meets all platform requirements
- Stable across target hardware configurations
- Ready for platform testing

## Quality Assessment:
- Platform Performance (40%)
- Requirements Compliance (40%)
- Hardware Compatibility (20%)

If score <95%: Continue optimization
```

## Phase 4: Final Certification

### If `--certification`, verify platform requirements:

```
Execute platform certification verification.

## Certification Checklist (platform-specific):

### General Requirements
- [ ] Content rating compliance
- [ ] Age rating appropriate
- [ ] No prohibited content
- [ ] Legal compliance

### Technical Requirements
- [ ] Meet platform performance guidelines
- [ ] Handle platform lifecycle events
- [ ] Comply with input guidelines
- [ ] Meet memory limits
- [ ] Handle network requirements (if applicable)

### UI/UX Requirements
- [ ] Platform UI guidelines followed
- [ ] Navigation works with platform input
- [ ] Platform-specific features implemented
- [ ] Accessibility requirements met

### Submission Requirements
- [ ] Required metadata complete
- [ ] Store assets prepared
- [ ] Screenshots provided
- [ ] Trailer/demo prepared
- [ ] Legal documents ready

### Platform-Specific Requirements
- [ ] Console-specific (if applicable)
- [ ] Mobile-specific (if applicable)
- [ ] PC-specific (if applicable)

## Issue Resolution:
For each certification failure:
1. Identify responsible agent
2. Implement fix
3. Re-verify compliance
4. Document resolution

## Expected Output:
- All certification requirements met
- No blocking issues
- Submission-ready build
- All submission materials prepared

## Quality Gate:
Zero certification failures
If failures remain: Must resolve before release
```

## Phase 5: Release Preparation

### Use ai-producer agent to coordinate release:

```
Use the ai-producer sub agent to prepare for game release.

## Context to Pass:
- Final game build
- Platform requirements
- Release timeline

## Release Preparation Tasks:
1. Final Build Creation:
   - Create release build
   - Verify build integrity
   - Test on target platform
   - Archive source code
2. Release Materials:
   - Write release notes
   - Prepare store page description
   - Create store assets (screenshots, trailers)
   - Prepare marketing materials
3. Documentation:
   - Create player guide
   - Write patch notes template
   - Document known issues
   - Prepare support contact info
4. Launch Planning:
   - Choose release date
   - Plan marketing activities
   - Set up community channels
   - Prepare launch day checklist

## Expected Output:
- Release build ready
- All submission materials prepared
- Launch plan documented
- Support infrastructure ready

## Quality Assessment:
- Build Quality (40%)
- Materials Completeness (30%)
- Launch Readiness (30%)
```

## 🛑 Release Approval Gate (Mandatory Stop Point) 🛑

**CRITICAL: You MUST stop here and wait for user approval**

After all phases are complete and quality score ≥95%:

1. **Present Release Summary**:
   ```markdown
   ## Polish Complete, Game Ready for Release ✓

   **Game**: {game_name}
   **Polish Focus**: {polish_scope_summary}

   **Polish Status**:
   - Critical Issues: ✓ All Resolved
   - Focused Polish: ✓ {focus_area} ({quality}%)
   - Platform Optimization: ✓ Complete ({quality}%)
   - Certification: ✓ {status} ({quality}%)
   - Release Preparation: ✓ Complete ({quality}%)

   **Overall Game Quality**: {average_score}%

   **Quality Achievements**:
   - Zero critical bugs
   - Performance meets platform requirements
   - {focus_area} polished to ≥95% quality
   - Certification requirements met
   - Build ready for submission

   **Final Metrics**:
   - Playable duration: {final_duration}
   - Frame rate: {stable_fps} FPS average
   - Load times: {max_load_time} maximum
   - Build size: {final_size}
   - Tested platforms: {platform_list}

   **Release Checklist**:
   - [ ] Release build created
   - [ ] Store assets prepared
   - [ ] Release notes written
   - [ ] Marketing materials ready
   - [ ] Support infrastructure in place
   - [ ] Legal requirements met

   **Known Issues**:
   - Critical: 0
   - Important: {count} (documented, non-blocking)
   - Minor: {count}

   **Recommendation**: {RELEASE / ADDITIONAL POLISH}

   **Next Steps**:
   - If approved: Submit to platform(s)
   - If deferred: Additional polish needed
   ```

2. **Quality Highlights**:
   - Improvements made during polish
   - Final quality metrics
   - Platform certification status

3. **Ask Explicitly**:
   **"Polish is complete ({quality_score}% quality). Game meets release quality standards. Ready to submit to platform(s)? (Reply 'yes' to release, 'no' for additional polish, or 'defer' to launch later)"**

4. **WAIT for user response**

5. **Response Handling**:
   - **'yes'**: Complete workflow, provide release instructions
   - **'no'**: Identify specific additional polish needed
   - **'defer'**: Complete workflow but note deferred launch

## Workflow Logic

### Phase Transitions
1. **Start → Phase 0**: Load expansion state, assess polish needs
2. **Phase 0 → Phase 1**: Plan complete, begin critical fixes
3. **Phase 1 → Phase 2**: Zero critical issues
4. **Phase 2 → Phase 3**: Focus area ≥95% quality
5. **Phase 3 → Phase 4**: Platform optimization ≥95% quality
6. **Phase 4 → Phase 5**: Certification complete (if required)
7. **Phase 5 → Approval Gate**: Release prep ≥95% quality
8. **Approval Gate → Release**: User approval to submit
9. **Approval Gate → Polish**: User requests additional work

### Quality Gates
- **Critical Issues**: Zero remaining
- **Focused Polish ≥95%**: Chosen area meets release quality
- **Platform Optimization ≥95%**: Meets all platform requirements
- **Certification**: Zero failures (if applicable)
- **Release Prep ≥95%**: All materials ready
- **Overall ≥95%**: Game meets release quality
- **Any phase below threshold**: Continue work

### Iteration Approach
- **Critical Issues**: Zero tolerance, must resolve all
- **Focused Polish**: Maximum 3 iterations
- **Platform Optimization**: Maximum 2 iterations
- **Certification**: Maximum 3 cycles to fix failures

## Execution Flow Summary

```mermaid
1. Receive command → Parse options
2. Check for content expansion completion
3. If not complete: Prompt to run content expansion first
4. If complete: Load and analyze
5. Define polish scope (Phase 0)
6. Create polish roadmap
7. Execute critical fixes (Phase 1)
8. Verify zero critical issues
9. Execute focused polish (Phase 2)
10. Assess focus area → Iterate until ≥95%
11. Execute platform optimization (Phase 3)
12. Assess optimization → Iterate if <95%
13. Execute certification (if --certification) (Phase 4)
14. Verify zero certification failures
15. Execute release preparation (Phase 5)
16. Assess readiness
17. 🛑 STOP and request release approval
18. Wait for user response
19. Handle response: release / polish / defer
```

## Output Format

Add to `./.claude/game/{game_name}/`:
```
08-polish-plan.md            # Polish roadmap
09-release-report.md          # Final release report
10-release-checklist.md       # Release checklist
```

Unity project output:
- Release-ready build
- Optimized for target platform
- Certified for platform submission (if applicable)
- All submission materials prepared

## Success Criteria
- **Zero Critical Issues**: No crashes, data loss, or blockers
- **Polish Quality**: Focused areas ≥95% quality
- **Platform Ready**: Meets all platform requirements
- **Performance**: Consistent acceptable performance
- **Certified**: Passes all certification requirements (if applicable)
- **Release Materials**: All submission assets prepared
- **Quality Threshold**: Overall ≥95% quality score
- **User Approval**: User confirms game is ready to release

## Important Reminders
- **Zero Critical Tolerance**: Don't release with known critical issues
- **Platform Compliance**: Must meet all platform requirements
- **Performance First**: Optimization before visual polish
- **Test on Hardware**: Verify on actual target platforms
- **Preserve Quality**: Don't break what works during polish
- **User Experience**: Polish should improve, not change, the experience
- **Release Ready**: Build must be submission-ready
- **User Control**: Don't release without explicit approval

## Polish vs Expansion

This workflow **finalizes** the game for release.

After polish approval:
- Game is ready for platform submission
- Proceed with store submission and launch

## Common Pitfalls to Avoid

1. **Polishing Too Early**: Don't polish before content is complete
2. **Changing Core Gameplay**: Polish is refinement, not redesign
3. **Ignoring Platform Requirements**: Certification failures block release
4. **Over-Polishing**: Diminishing returns, know when to stop
5. **Breaking Fixes**: New bugs introduced during polish
6. **Performance Neglect**: Pretty but unplayable is not release-ready
7. **Skipping Certification**: Platform requirements are mandatory

## Release Decision Framework

If user asks for release recommendation, assess:

```markdown
## Release Readiness Assessment

### Green Light (Release) if:
- Quality score ≥95%
- Zero critical issues
- Platform certification passed
- Performance acceptable
- All planned features complete

### Yellow Light (Caution) if:
- Quality score 90-94%
- Important issues documented but non-blocking
- Some features cut but game complete
- Minor performance issues on some hardware

### Red Light (Don't Release) if:
- Quality score <90%
- Any critical issues remaining
- Certification failures
- Performance below platform minimum
- Major features incomplete
```
