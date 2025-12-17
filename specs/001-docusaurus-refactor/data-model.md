# Data Model: Physical AI & Humanoid Robotics Course

**Feature**: 001-docusaurus-refactor
**Date**: 2025-12-15

## Entities

### Course Module
- **Description**: Represents a major section of the course curriculum, containing lessons, examples, and exercises
- **Fields**:
  - id: string (e.g., "module-01", "module-02", etc.)
  - title: string (e.g., "The Robotic Nervous System", "The Digital Twin", etc.)
  - description: string (brief overview of module content)
  - lessons: array of Lesson entities
  - prerequisites: array of string (what students should know before starting)
  - learningObjectives: array of string (what students will learn)
- **Relationships**: Contains multiple Lesson entities

### Lesson
- **Description**: Individual content page with text, code examples, and media for learning
- **Fields**:
  - id: string (unique identifier within module)
  - title: string (lesson title)
  - content: string (markdown content)
  - module: reference to Course Module
  - prerequisites: array of string
  - learningObjectives: array of string
  - codeExamples: array of CodeExample
- **Relationships**: Belongs to one Course Module

### Code Example
- **Description**: Programming example with syntax highlighting for educational purposes
- **Fields**:
  - id: string (unique identifier)
  - language: string (e.g., "python", "cpp", "bash")
  - code: string (the actual code content)
  - description: string (explanation of what the code does)
  - lesson: reference to Lesson
- **Relationships**: Belongs to one Lesson

### Navigation Structure
- **Description**: Organized menu system that allows students to navigate between course modules
- **Fields**:
  - id: string (unique identifier)
  - label: string (display name in navigation)
  - link: string (URL path to content)
  - children: array of Navigation Structure (for sub-menu items)
  - module: reference to Course Module (optional, for module-specific navigation)
- **Relationships**: May reference Course Module

## Validation Rules

### Course Module Validation
- Title must be non-empty
- Must have at least one lesson
- Learning objectives must be defined
- ID must follow the pattern "module-{number}"

### Lesson Validation
- Title must be non-empty
- Content must be non-empty
- Must belong to a valid Course Module
- Learning objectives should align with parent module

### Code Example Validation
- Language must be one of: "python", "cpp", "bash", "typescript", "javascript", "json"
- Code content must be non-empty
- Must belong to a valid Lesson

## State Transitions

### Content Development States
- DRAFT: Initial state when creating content
- REVIEW: Content ready for review by course team
- APPROVED: Content approved for student access
- PUBLISHED: Content live and accessible to students

## Assumptions

1. All content will be stored as static markdown files
2. Navigation will be generated from the structure defined in sidebars.ts
3. Code examples will be embedded directly in markdown files using Docusaurus code blocks
4. Module numbering will be sequential (module-01, module-02, etc.)