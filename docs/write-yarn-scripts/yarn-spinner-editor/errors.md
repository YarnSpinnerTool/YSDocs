---
description: The errors that Yarn Spinner can emit.
---

# Errors

## Yarn Spinner Error Codes

### Errors

| Code   | Message                                                                                                                                     |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| YS0001 | Variable has conflicting implicit type declarations. A variable is being used as different types in different places.                       |
| YS0002 | Type mismatch. An expression's type doesn't match what's expected (e.g. assigning a number to a boolean).                                   |
| YS0004 | Missing node delimiter. A node is missing its `===` closing delimiter.                                                                      |
| YS0005 | Syntax error. Something in the script can't be parsed.                                                                                      |
| YS0006 | Unclosed command. A `<<` was opened but never closed with `>>`.                                                                             |
| YS0007 | Unclosed scope. A control flow block (like `<<if>>`) isn't properly closed (missing `<<endif>>`).                                           |
| YS0011 | Duplicate node title. Two or more nodes have the same title without `when:` clauses to distinguish them.                                    |
| YS0012 | Jump to undefined node. A `<<jump>>` or `<<detour>>` targets a node that doesn't exist.                                                     |
| YS0013 | Invalid function call. A function is called with the wrong number or type of parameters, or doesn't exist.                                  |
| YS0014 | Invalid or unknown command. A command isn't recognised. Check spelling or make sure it's defined in your definitions file.                  |
| YS0017 | Line has both `#line` and `#shadow` tags. A line can't be both — shadow lines don't get their own line ID.                                  |
| YS0018 | Duplicate line ID. Every `#line:` tag in a project must be unique.                                                                          |
| YS0021 | Stray `>>` without a matching `<<`.                                                                                                         |
| YS0022 | Command keyword outside of `<<` and `>>`. Did you forget the angle brackets?                                                                |
| YS0025 | Unknown enum member. The value isn't a known member of the expected enum type.                                                              |
| YS0023 | Wrong enum type. The value is from a different enum than what the parameter expects.                                                        |
| YS0024 | Enum type expected. The parameter expects an enum value but got something else.                                                             |
| YS0026 | Enum format error. Enum values should be written as `EnumName.Value`.                                                                       |
| YS0027 | Invalid node name. Node titles can only contain letters, numbers, and underscores.                                                          |
| YS0028 | Can't infer variable type. Declare the variable explicitly with `<<declare>>`.                                                              |
| YS0029 | Can't determine expression type. The compiler can't figure out what type this expression evaluates to.                                      |
| YS0030 | Can't modify a smart variable. Smart variables are computed values and are read-only.                                                       |
| YS0031 | Missing `when:` clause in node group. If some nodes in a group have `when:` clauses, all must have them (use `when: always` as a fallback). |
| YS0032 | Duplicate subtitle in node group. Subtitles within a node group must be unique.                                                             |
| YS0034 | Incompatible function. A library function has a signature that can't be used in Yarn scripts.                                               |
| YS0035 | Enum declaration error.                                                                                                                     |
| YS0036 | Feature requires newer project version. A language feature was used that needs a higher `projectFileVersion`.                               |
| YS0037 | Invalid literal value. A constant value couldn't be parsed.                                                                                 |
| YS0038 | Unresolved type member. A type member access (like `Enum.Value`) couldn't be resolved.                                                      |
| YS0039 | Variable redeclaration. A variable can only be declared once.                                                                               |
| YS0040 | Type redeclaration. A type with this name already exists.                                                                                   |
| YS0041 | Internal compiler error. Something unexpected happened. Please file an issue.                                                               |
| YS0042 | Unknown line ID for shadow line. The `#shadow:` tag references a line ID that doesn't exist.                                                |
| YS0043 | Shadow lines can't have expressions. Shadow lines must be plain text.                                                                       |
| YS0044 | Shadow line text mismatch. A shadow line must have the same text as its source line.                                                        |
| YS0045 | Smart variable reference loop. A smart variable's expression references itself through other smart variables.                               |
| YS0046 | Null default value. Variable declarations must have a non-null default value.                                                               |
| YS0047 | Expression took too long to resolve. Try simplifying this expression.                                                                       |

### Warnings

| Code   | Message                                                                                                                 |
| ------ | ----------------------------------------------------------------------------------------------------------------------- |
| YS0003 | Undeclared variable. A variable is used without being declared. Add a `<<declare>>` statement.                          |
| YS0008 | Unreachable code. Code that will never be executed.                                                                     |
| YS0015 | Cyclic node dependency. Nodes reference each other in a loop, which may cause infinite loops.                           |
| YS0016 | Unknown character. A character name isn't defined in the project. Add it to your `.yarnproject` file's characters list. |

### Info

| Code   | Message                                                          |
| ------ | ---------------------------------------------------------------- |
| YS0010 | Unused variable. A variable is declared but never used anywhere. |
