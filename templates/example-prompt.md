# Code Review Assistant

## Description
A thorough code review prompt that analyzes code for bugs, performance issues, and best practices.

## Prompt
Review the following {{language}} code and provide feedback on:

1. **Bugs & Errors**: Any logical errors or potential runtime issues
2. **Performance**: Inefficiencies or optimization opportunities
3. **Best Practices**: Adherence to {{language}} conventions
4. **Security**: Any security vulnerabilities
5. **Readability**: Code clarity and documentation

Code to review:
```{{language}}
{{code}}
```

Provide specific line references and suggested fixes for each issue found.

## Variables
- `{{language}}`: Programming language (e.g., Python, TypeScript)
- `{{code}}`: The code snippet to review

## Example
Review the following Python code and provide feedback on:
...
```python
def get_user(id):
    return db.query(f"SELECT * FROM users WHERE id = {id}")
```

## Notes
- Works best with code snippets under 500 lines
- Specify the language for more accurate feedback
- Can add specific focus areas (e.g., "focus on security")
