# Quickstart Guide: Physical AI & Humanoid Robotics Course

**Feature**: 001-docusaurus-refactor
**Date**: 2025-12-15

## Getting Started with Development

### Prerequisites
- Node.js 18+ installed
- npm or yarn package manager
- Git for version control

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start development server**
   ```bash
   npm run start
   # or
   yarn start
   ```
   This will start the Docusaurus development server at http://localhost:3000

4. **Build for production**
   ```bash
   npm run build
   # or
   yarn build
   ```

### Project Structure Overview

```
my-website/
├── docs/                 # Course content (modules and lessons)
│   ├── module-01/        # Module 1: The Robotic Nervous System (ROS 2)
│   ├── module-02/        # Module 2: The Digital Twin (Gazebo & Unity)
│   ├── module-03/        # Module 3: The AI-Robot Brain (NVIDIA Isaac)
│   └── module-04/        # Module 4: Vision-Language-Action (VLA)
├── src/                  # Custom React components
├── static/               # Static assets
├── docusaurus.config.ts  # Site configuration
├── sidebars.ts           # Navigation structure
└── package.json          # Dependencies and scripts
```

### Adding New Content

1. **Create a new lesson** in the appropriate module directory:
   ```bash
   # Create a new lesson in module-01
   touch docs/module-01/new-lesson.md
   ```

2. **Add frontmatter** to your lesson file:
   ```markdown
   ---
   title: Lesson Title
   sidebar_position: 1
   description: Brief description of the lesson
   ---
   ```

3. **Update sidebars.ts** to include your new lesson in the navigation

### Code Examples

To add code examples with syntax highlighting:

```python
# Python example
def hello_ros():
    print("Hello ROS 2!")
```

```cpp
// C++ example
#include <iostream>
int main() {
    std::cout << "Hello from C++!" << std::endl;
    return 0;
}
```

### Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the main branch. The workflow is configured in `.github/workflows/deploy.yml`.

To manually trigger a deployment:
1. Commit your changes
2. Push to the main branch
3. The GitHub Actions workflow will build and deploy the site

### Common Commands

- `npm run start` - Start local development server
- `npm run build` - Build static files for production
- `npm run serve` - Serve the built site locally
- `npm run deploy` - Deploy to GitHub Pages (if configured)

### Troubleshooting

- If you encounter issues with the build, try clearing the cache:
  ```bash
  npm run clear
  ```

- For dependency issues, try:
  ```bash
  rm -rf node_modules package-lock.json
  npm install
  ```