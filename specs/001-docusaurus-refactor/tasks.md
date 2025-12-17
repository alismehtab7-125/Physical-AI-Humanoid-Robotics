---
description: "Task list for Docusaurus refactoring to Physical AI & Humanoid Robotics course"
---

# Tasks: Physical AI & Humanoid Robotics Course

**Input**: Design documents from `/specs/001-docusaurus-refactor/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: The examples below include test tasks. Tests are OPTIONAL - only include them if explicitly requested in the feature specification.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Docusaurus project**: `docs/`, `src/`, `static/` at repository root with `docusaurus.config.ts` and `sidebars.ts`
- Paths shown below assume Docusaurus project structure based on plan.md

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic structure

- [x] T001 Create my-website directory structure per implementation plan
- [x] T002 [P] Check if existing Docusaurus project exists and identify default content to remove
- [x] T003 [P] Verify Node.js and npm are available for Docusaurus development

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Core infrastructure that MUST be complete before ANY user story can be implemented

**⚠️ CRITICAL**: No user story work can begin until this phase is complete

- [x] T004 Identify and list all default Docusaurus files to remove (blog/, tutorial/, intro.md, etc.)
- [x] T005 Verify docusaurus.config.ts file exists and location
- [x] T006 Verify sidebars.ts file exists and location

**Checkpoint**: Foundation ready - user story implementation can now begin in parallel

---

## Phase 3: User Story 1 - Course Content Access (Priority: P1) 🎯 MVP

**Goal**: Create the foundational course structure with 4 modules accessible to students

**Independent Test**: Students can navigate to the main page and see 4 clearly labeled modules with clear navigation paths

### Implementation for User Story 1

- [x] T007 [P] [US1] Update docusaurus.config.ts title to "Physical AI & Humanoid Robotics"
- [x] T008 [P] [US1] Update docusaurus.config.ts tagline to "A comprehensive course on robotics and AI"
- [x] T009 [P] [US1] Configure GitHub Pages settings in docusaurus.config.ts
- [x] T010 [P] [US1] Create directory docs/module-01 for "The Robotic Nervous System (ROS 2)"
- [x] T011 [P] [US1] Create directory docs/module-02 for "The Digital Twin (Gazebo & Unity)"
- [x] T012 [P] [US1] Create directory docs/module-03 for "The AI-Robot Brain (NVIDIA Isaac)"
- [x] T013 [P] [US1] Create directory docs/module-04 for "Vision-Language-Action (VLA)"
- [x] T014 [US1] Create initial index.md files for each module directory
- [x] T015 [US1] Create sidebars.ts with navigation structure for the 4 modules
- [x] T016 [US1] Update docusaurus.config.ts to enable dark mode support
- [x] T017 [US1] Configure Python/C++ syntax highlighting in docusaurus.config.ts

**Checkpoint**: At this point, User Story 1 should be fully functional and testable independently

---

## Phase 4: User Story 2 - Clean Learning Environment (Priority: P1)

**Goal**: Remove default Docusaurus content to create a focused learning environment without distractions

**Independent Test**: Students can navigate through the course content without encountering any default Docusaurus pages or unrelated content

### Implementation for User Story 2

- [x] T018 [P] [US2] Remove default blog directory and related configuration
- [x] T019 [P] [US2] Remove default tutorial directory and related configuration
- [x] T020 [P] [US2] Remove default intro.md and any other default content files
- [x] T021 [US2] Update docusaurus.config.ts to remove references to default content
- [x] T022 [US2] Update sidebars.ts to remove default content navigation links
- [x] T023 [US2] Verify no default Docusaurus content appears in navigation

**Checkpoint**: At this point, User Stories 1 AND 2 should both work independently

---

## Phase 5: User Story 3 - Code Example Support (Priority: P2)

**Goal**: Ensure proper syntax highlighting for Python and C++ code examples in course documentation

**Independent Test**: Students can view Python and C++ code examples with proper syntax highlighting that makes the code readable and easy to understand

### Implementation for User Story 3

- [ ] T024 [P] [US3] Add Python code example placeholder to module-01/index.md
- [ ] T025 [P] [US3] Add C++ code example placeholder to module-01/index.md
- [ ] T026 [US3] Verify syntax highlighting works correctly for Python code blocks
- [ ] T027 [US3] Verify syntax highlighting works correctly for C++ code blocks
- [ ] T028 [US3] Add syntax highlighting configuration for both languages in docusaurus.config.ts

**Checkpoint**: At this point, User Stories 1, 2 AND 3 should all work independently

---

## Phase 6: User Story 4 - Dark Mode Accessibility (Priority: P2)

**Goal**: Enable dark mode toggle functionality for improved accessibility and user comfort

**Independent Test**: Students can switch between light and dark themes using the theme toggle functionality

### Implementation for User Story 4

- [ ] T029 [US4] Verify dark mode toggle appears in the UI
- [ ] T030 [US4] Test dark mode functionality across all modules
- [ ] T031 [US4] Ensure all content is readable in both light and dark modes
- [ ] T032 [US4] Configure default theme preference in docusaurus.config.ts

**Checkpoint**: All user stories should now be independently functional

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Improvements that affect multiple user stories

- [ ] T033 [P] Add initial content to module index files with learning objectives
- [ ] T034 [P] Verify responsive design works on mobile and desktop
- [ ] T035 Update navigation titles to match module names clearly
- [ ] T036 Add GitHub Pages deployment workflow configuration
- [ ] T037 Run local Docusaurus build to validate all changes
- [ ] T038 Run quickstart.md validation to ensure setup instructions work

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS all user stories
- **User Stories (Phase 3+)**: All depend on Foundational phase completion
  - User stories can then proceed in parallel (if staffed)
  - Or sequentially in priority order (P1 → P2 → P3)
- **Polish (Final Phase)**: Depends on all desired user stories being complete

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Foundational (Phase 2) - No dependencies on other stories
- **User Story 2 (P2)**: Can start after Foundational (Phase 2) - May integrate with US1 but should be independently testable
- **User Story 3 (P3)**: Can start after Foundational (Phase 2) - May integrate with US1/US2 but should be independently testable
- **User Story 4 (P4)**: Can start after Foundational (Phase 2) - May integrate with other stories but should be independently testable

### Within Each User Story

- Core implementation before integration
- Story complete before moving to next priority

### Parallel Opportunities

- All Setup tasks marked [P] can run in parallel
- All Foundational tasks marked [P] can run in parallel (within Phase 2)
- Once Foundational phase completes, all user stories can start in parallel (if team capacity allows)
- Models within a story marked [P] can run in parallel
- Different user stories can be worked on in parallel by different team members

---

## Parallel Example: User Story 1

```bash
# Launch all configuration updates together:
Task: "Update docusaurus.config.ts title to 'Physical AI & Humanoid Robotics'"
Task: "Update docusaurus.config.ts tagline to 'A comprehensive course on robotics and AI'"
Task: "Configure GitHub Pages settings in docusaurus.config.ts"

# Launch all module directory creations together:
Task: "Create directory docs/module-01 for 'The Robotic Nervous System (ROS 2)'"
Task: "Create directory docs/module-02 for 'The Digital Twin (Gazebo & Unity)'"
Task: "Create directory docs/module-03 for 'The AI-Robot Brain (NVIDIA Isaac)'"
Task: "Create directory docs/module-04 for 'Vision-Language-Action (VLA)'"
```

---

## Implementation Strategy

### MVP First (User Stories 1 and 2 Only)

1. Complete Phase 1: Setup
2. Complete Phase 2: Foundational (CRITICAL - blocks all stories)
3. Complete Phase 3: User Story 1
4. Complete Phase 4: User Story 2
5. **STOP and VALIDATE**: Test User Stories 1 and 2 independently
6. Deploy/demo if ready

### Incremental Delivery

1. Complete Setup + Foundational → Foundation ready
2. Add User Story 1 + 2 → Test independently → Deploy/Demo (MVP!)
3. Add User Story 3 → Test independently → Deploy/Demo
4. Add User Story 4 → Test independently → Deploy/Demo
5. Each story adds value without breaking previous stories

### Parallel Team Strategy

With multiple developers:

1. Team completes Setup + Foundational together
2. Once Foundational is done:
   - Developer A: User Story 1
   - Developer B: User Story 2
   - Developer C: User Story 3
   - Developer D: User Story 4
3. Stories complete and integrate independently

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- Each user story should be independently completable and testable
- Verify tests fail before implementing
- Commit after each task or logical group
- Stop at any checkpoint to validate story independently
- Avoid: vague tasks, same file conflicts, cross-story dependencies that break independence