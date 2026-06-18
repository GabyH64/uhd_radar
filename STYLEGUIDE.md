Naming conventions:

- Modifiable parameters, variables
  - Lowercase, with \_ instead of spaces between words
  - Ex: chirp_length, pulse_length, sample_rate
- Functions
  - All words after first start uppercase, no spaces between words
  - Ex: loadSamplesFromFile, plotChirpVsTime, findDirectPath
- Constants
  - Constants should start with k, after which all words should start uppercase, with no spaces between words
  - Ex. kConstantValue
- Classes and Structs
  - Each word should start uppercase, with no spaces between words
  - Ex. ClassName
- Macros
  - All uppercase separated by underscores
  - Ex. BIT_MASK

Indent size:

- Use spaces instead of tabs
- Python: Use 4 space indents
- C/C++: TODO 2 or 4? Currently C files have 2 space indents, 4 is standard practice

When to add comments:

- Before functions
  - Contain summary of purpose of function and all inputs used for function
  - Ex: before function doubleNumber(number), add a comment stating "This function doubles the given number. number - the number meant to be doubled"
- In functions
  - On longer functions where the logic is unclear, add comments between steps to describe what the next step does
  - Ex: Between two steps, write "Now calculate change from one variable to the next" if one process is finished and another is starting
- Clarifications
  - If a step of a function is more complicated or harder to read, explain what the step is doing, and what output is expected

File names:

- Lowercase, with \_ instead of spaces between words
- Ex: preprocessing, testing

Unit Tests

- Unit tests must be made within the tests/ directory in a file that starts with tests*(ex test_generate_chirp.py) and the test function must also start with test* . Each function should have its own unit tests with the same file structure as the source code for example if the function being tested is preprocessing/generate_chirp.py: generate_from_yaml_filename(yaml_filename), the corresponding test should be tests/preprocessing/test_generate_chirp.py: test_generate_from_yaml_filename().
- For C++ tests, you can specify the test suite name (ie. The name of the function being tested) as well as the case being tested (ie. The specific set of inputs for the function). This is done like TEST(SuiteName, CaseName) {...}.

Doxygen Requirements:

- **Comment Block Structure:** Include optional brief (one-liner) and detailed descriptions. Methods/functions can also have an "in body" description from comments within their body. Avoid multiple brief/detailed descriptions for clarity. Brief descriptions are used for tooltips and member overviews. Separate brief and detailed descriptions with an empty line or use JAVADOC_AUTOBRIEF.
- **Documentation Placement:** Place documentation blocks in front of declarations/definitions. For members/parameters, documentation can be placed after them by adding a < marker (e.g., /\*!<, /\*\*<, //!<, ///<). These "after-member" blocks are only for members and parameters, not files, classes, or structural commands. Documentation can also be placed in source files (before definitions) to keep headers compact. For global objects (functions, typedefs, enums, macros), you must document the file they are defined in with /\*! \\file \*/ or /\*\* @file \*/.
- **Special Comment Blocks & Structural Commands:**
  - Use C/C++ style comments with special markings like
    - /// / //! (C++ lines)
    - Blank lines end /// or //! blocks.
  - For increased visibility, use banner-style comments
    - (e.g., /\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*//\*\* ... \*/ or /////////////////// /// ...).
  - Structural commands (e.g., \\class, \\fn, \\var) link documentation blocks to specific code entities, allowing flexible placement. However, avoid them if the comment block is directly before/after an item, as they create redundant information and can lead to problems.
- **Language-Specific Conventions:**
  - C-like (C/C++/C#/Objective-C/PHP/Java): Javadoc, Qt, ///, //! styles.
  - Python: Use """! for Doxygen commands in docstrings, or ##/##< comments.
- **Formatting within Comments:** Support plain text, Markdown (including Markdown Extra), Javadoc-like (\\ or @ commands), XML markup (C# standard), and a subset of HTML.
