```markdown
# BMAD-METHOD Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development conventions and workflows used in the BMAD-METHOD TypeScript codebase. It covers file naming, import/export styles, commit message patterns, and testing practices to ensure consistency and maintainability across the project.

## Coding Conventions

### File Naming
- Use **kebab-case** for all file names.
  - Example:  
    ```
    my-component.ts
    user-service.test.ts
    ```

### Import Style
- Use **relative imports** for referencing modules within the project.
  - Example:
    ```typescript
    import { myFunction } from './utils';
    ```

### Export Style
- Use **named exports** for all modules.
  - Example:
    ```typescript
    // utils.ts
    export function myFunction() { /* ... */ }
    ```

### Commit Messages
- Follow the **conventional commit** format.
- Use the `chore` prefix for maintenance commits.
- Keep commit messages concise (average ~76 characters).
  - Example:
    ```
    chore: update dependencies to latest versions
    ```

## Workflows

### Commit Changes
**Trigger:** When making any code change that needs to be tracked.
**Command:** `/commit-changes`

1. Stage your changes:
    ```
    git add .
    ```
2. Write a conventional commit message, using the `chore` prefix when appropriate:
    ```
    git commit -m "chore: describe your change here"
    ```
3. Push your changes:
    ```
    git push
    ```

### Add a New Module
**Trigger:** When creating a new functionality or utility.
**Command:** `/add-module`

1. Create a new file using kebab-case naming:
    ```
    touch new-feature.ts
    ```
2. Use named exports in the new file:
    ```typescript
    export function newFeature() { /* ... */ }
    ```
3. Import the module using a relative path where needed:
    ```typescript
    import { newFeature } from './new-feature';
    ```

### Write a Test
**Trigger:** When adding or updating functionality.
**Command:** `/write-test`

1. Create a test file with the `.test.` pattern, using kebab-case:
    ```
    touch new-feature.test.ts
    ```
2. Write your test cases in the new file.
3. Ensure the test framework (unknown, check project docs) is used correctly.

## Testing Patterns

- Test files follow the `*.test.*` naming convention and are written in TypeScript.
- The specific test framework is not detected; refer to project documentation for details.
- Example test file:
    ```typescript
    // math-utils.test.ts
    import { add } from './math-utils';

    describe('add', () => {
      it('adds two numbers', () => {
        expect(add(2, 3)).toBe(5);
      });
    });
    ```

## Commands
| Command         | Purpose                                      |
|-----------------|----------------------------------------------|
| /commit-changes | Guide for staging, committing, and pushing   |
| /add-module     | Steps for creating and importing a new module|
| /write-test     | Steps for creating and writing a test file   |
```
