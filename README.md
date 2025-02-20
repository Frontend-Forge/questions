Please Move through this Readme before adding questions.
## Question Structure
Each question in the platform consists of the following components:

### File Structure
```typescript
type File = {
  name: string;
  language: "javascript" | "css" | "html";
  content: string;
};
```

Each challenge includes:
- Initial starter files (both vanilla and React versions)
- Solution files (both vanilla and React versions)

### Question Details

#### Basic Information
- **Name**: Challenge title
- **Difficulty**: Easy, Medium, or Hard
- **Time**: Expected completion time in minutes
- **Question Type**: 
  - `ui`: UI implementation challenges
  - `logical`: Algorithm/logic-based problems

#### Technical Details
- **Tech Stack**: Array of technologies used (`html`, `css`, `js`, `react`)
- **Companies**: Companies known to ask similar questions (Google, Facebook, Twitter, Apple, Microsoft)

#### Content
- **Question Description**: Detailed problem statement
- **Requirements**: Array of specific requirements to be met
- **Notes**: Additional hints or important information
- **Test Cases** (Only for logical questions):
  ```typescript
  type TestCases = {
    input: number[] | string | number | object;
    output: number | boolean | string | number[] | object;
    description: string;
  };
  ```

#### Author Information
```typescript
type QuestionerInfo = {
  name: String;
  profilePic: string;
  additionalInfo?: string;
};
```

## Contributing

### Adding a New Question

1. Fork this repository
2. See the example Questions below before creating a new question
3. Create a new question following this structure:

```json
{
  "initialVanillaFiles": [
    {
      "name": "index.html",
      "language": "html",
      "content": "<!-- Your starter HTML -->"
    }
    // Add other starter files
  ],
  "initialReactFiles": [
    // React version starter files
  ],
  "solutionVanillaFiles": [
    // Vanilla JS solution files
  ],
  "solutionReactFiles": [
    // React solution files
  ],
  "questionDetails": {
    "name": "Your Question Title",
    "questionaerInfo": {
      "name": "Your Name",
      "profilePic": "URL to profile picture"
    },
    "techStack": ["html", "css", "js"],
    "difficulty": "Medium",
    "time": 30,
    "questionDescription": "Detailed description of the problem",
    "requirements": [
      "Requirement 1",
      "Requirement 2"
    ],
    "notes": [
      "Helpful note 1",
      "Helpful note 2"
    ],
    "companies": ["Google", "Facebook"],
    "questionType": "ui"
    // Include testCases if questionType is "logical"
  }
}
```

### Guidelines for Question Creation

1. **UI Questions**:
   - Should focus on real-world UI components
   - Must include both vanilla and React implementations
   - Should specify all required features clearly
   - Include responsive design requirements if applicable

2. **Logical Questions**:
   - Should include only vanilla JS implementation , you can assign empty array to react Implementation (See the logical question example below)
   - Must include test cases with inputs and expected outputs
   - Should cover edge cases
   - Test cases should have clear descriptions

3. **General Guidelines**:
   - Provide clear, concise descriptions
   - Include all necessary starter code
   - Specify accurate time estimates
   - Tag relevant companies if applicable
   - Include helpful notes without giving away the solution

## Code Stringification Guide

### Before Adding Code to Questions

All code content must be properly stringified before adding to the question JSON. Here's how to prepare your code:

```javascript
// Example code preparation
const myCode = `
function example() {
  console.log("Hello");
}
`;

// Stringify the code before adding to question
const stringifiedCode = JSON.stringify(myCode);
// Now use this stringifiedCode in your question JSON
```

### Example Question Structure with Stringified Code

```javascript
{
  "initialVanillaFiles": [
    {
      "name": "index.js",
      "language": "javascript",
      "content": "\"function example() {\\n  console.log(\\\"Hello\\\");\\n}\"" // Note the escaped quotes and newlines
    }
  ]
}
```

### Tools for Code Stringification

1. **Online Tools (Recommended)**
   - [JSON Editor Online](https://jsoneditoronline.org/)
   - Steps:
     1. Paste your code into the left panel
     2. Click the right arrow to format
     3. Copy the stringified version

2. **Using Browser Console**
   ```javascript
   // Paste this in browser console
   copy(JSON.stringify(`your code here`))
   // Stringified code is now in your clipboard
   ```

3. **Using Node.js**
   ```bash
   node -e "console.log(JSON.stringify(\`your code here\`))"
   ```

### Common Mistakes to Avoid

1. ❌ Don't add raw code:
   ```javascript
   {
     "content": "function example() {
       console.log("Hello");
     }"
   }
   ```

2. ✅ Do add stringified code:
   ```javascript
   {
     "content": "\"function example() {\\n  console.log(\\\"Hello\\\");\\n}\""
   }
   ```

### Quick Guide for Different File Types

1. **For JavaScript Files**
   ```javascript
   const jsCode = `
   function example() {
     return true;
   }
   `;
   const stringified = JSON.stringify(jsCode);
   ```

2. **For HTML Files**
   ```javascript
   const htmlCode = `
   <!DOCTYPE html>
   <html>
     <body>
       <h1>Hello</h1>
     </body>
   </html>
   `;
   const stringified = JSON.stringify(htmlCode);
   ```

3. **For CSS Files**
   ```javascript
   const cssCode = `
   body {
     margin: 0;
     padding: 0;
   }
   `;
   const stringified = JSON.stringify(cssCode);
   ```

### Example Command for Multiple Files

```javascript
// Helper function to stringify multiple files
function stringifyFiles(files) {
  return files.map(file => ({
    ...file,
    content: JSON.stringify(file.content)
  }));
}

// Usage
const files = [
  {
    name: "index.js",
    language: "javascript",
    content: `function example() {
      return true;
    }`
  }
];

const stringifiedFiles = stringifyFiles(files);
```

### Using Visual Studio Code

1. Install "JSON Tools" extension
2. Select your code
3. Right-click > Command Palette
4. Select "Stringify"

### Validation

Always validate your stringified code:
1. Try parsing it back:
   ```javascript
   const isValid = (str) => {
     try {
       JSON.parse(str);
       return true;
     } catch {
       return false;
     }
   }
   ```

2. Check for common issues:
   - All quotes are properly escaped
   - All newlines are `\n`
   - No unescaped special characters


## Question Review Process

1. Questions are reviewed for:
   - Technical accuracy
   - Clarity of requirements
   - Completeness of test cases (for logical questions)
   - Code quality in solutions
   - Appropriate difficulty rating

2. Feedback will be provided through PR comments

3. Once approved, questions will be added to the main database

# Frontend Challenge Question Examples

## 1. UI Question Example: Todo List

```json
{
      "initialVanillaFiles": [
        {
          "name": "index.html",
          "language": "html",
          "content": "<!doctype html>\n<html>\n  <head>\n    <meta charset=\"UTF-8\" />\n    <meta\n      name=\"viewport\"\n      content=\"width=device-width, initial-scale=1.0\" />\n  </head>\n  <body>\n    <div>\n      <h1>Todo List</h1>\n      <div>\n        <input type=\"text\" placeholder=\"Add your task\" />\n        <div>\n          <button>Submit</button>\n        </div>\n      </div>\n      <ul>\n        <li>\n          <span>Walk the dog</span>\n          <button>Delete</button>\n        </li>\n        <li>\n          <span>Water the plants</span>\n          <button>Delete</button>\n        </li>\n        <li>\n          <span>Wash the dishes</span>\n          <button>Delete</button>\n        </li>\n      </ul>\n    </div>\n  </body>\n</html>\n\n\n\n"
        },
        {
          "name": "style.css",
          "language": "css",
          "content": "body {\n  font-family: sans-serif;\n}\n\n"
        },
        {
          "name": "index.js",
          "language": "javascript",
          "content": "// Write your JavaScript here.\n\n"
        }
      ],
      "initialReactFiles": [
        {
          "name": "public/index.html",
          "language": "html",
          "content": "<!DOCTYPE html>\n  <html>\n  <head>\n    <title>React App</title>\n  </head>\n  <body>\n    <div id=\"root\"></div>\n  </body>\n  </html>"
        },
        {
          "name": "src/App.js",
          "language": "javascript",
          "content": "\nfunction App() {\n  return (\n    <div>\n      <h1>Todo List</h1>\n      <div>\n        <input type=\"text\" placeholder=\"Add your task\" />\n        <div>\n          <button>Submit</button>\n        </div>\n      </div>\n      <ul>\n        <li>\n          <span>Walk the dog</span>\n          <button>Delete</button>\n        </li>\n        <li>\n          <span>Water the plants</span>\n          <button>Delete</button>\n        </li>\n        <li>\n          <span>Wash the dishes</span>\n          <button>Delete</button>\n        </li>\n      </ul>\n    </div>\n  );\n}\n\n"
        },
        {
          "name": "src/index.js",
          "language": "javascript",
          "content": "const root = ReactDOM.createRoot(document.getElementById('root'));\n  root.render(\n    <React.StrictMode>\n      <App />\n    </React.StrictMode>\n  );"
        },
        {
          "name": "src/style.css",
          "language": "css",
          "content": "body {\n  font-family: sans-serif;\n}\n"
        }
      ],
      "solutionVanillaFiles": [
        {
          "name": "index.html",
          "language": "html",
          "content": "<!doctype html>\n<html>\n  <head>\n    <meta charset=\"UTF-8\" />\n    <meta\n      name=\"viewport\"\n      content=\"width=device-width, initial-scale=1.0\" />\n  </head>\n  <body>\n    <div>\n      <h1>Todo List</h1>\n      <div>\n        <input\n          aria-label=\"Add new task\"\n          type=\"text\"\n          placeholder=\"Add your task\" />\n        <div>\n          <button id=\"submit\">Submit</button>\n        </div>\n      </div>\n      <ul>\n        <li>\n          <span>Walk the dog</span>\n          <button>Delete</button>\n        </li>\n        <li>\n          <span>Water the plants</span>\n          <button>Delete</button>\n        </li>\n        <li>\n          <span>Wash the dishes</span>\n          <button>Delete</button>\n        </li>\n      </ul>\n    </div>\n    <script src=\"src/index.js\"></script>\n  </body>\n</html>\n\n\n\n"
        },
        {
          "name": "style.css",
          "language": "css",
          "content": "body {\n  font-family: sans-serif;\n}\n"
        },
        {
          "name": "index.js",
          "language": "javascript",
          "content": "\n(() => {\n  // Retain a reference to the elements which persist\n  // throughout usage of the app.\n  const $inputEl = document.querySelector('input');\n  const $submitButtonEl = document.querySelector('#submit');\n  const $todoListEl = document.querySelector('ul');\n\n  function addTask(label) {\n    // Create the DOM elements for the new task.\n    const $newTaskElement = document.createElement('li');\n\n    const $span = document.createElement('span');\n    $newTaskElement.appendChild($span);\n    // Using Node.textContent here instead of Element.innerHTML\n    // to prevent XSS (Cross Site Scripting).\n    $span.textContent = label;\n\n    const $btn = document.createElement('button');\n    $btn.textContent = 'Delete';\n    $newTaskElement.appendChild($btn);\n\n    // Add the new task to the list.\n    $todoListEl.append($newTaskElement);\n  }\n\n  function deleteTask($itemEl) {\n    // Remove the task from the list.\n    $itemEl.parentNode.removeChild($itemEl);\n  }\n\n  $submitButtonEl.addEventListener('click', () => {\n    addTask($inputEl.value);\n    // Reset the input so that new tasks can be added.\n    $inputEl.value = '';\n  });\n\n  // Add a listener to the list instead of individual tasks.\n  // This is called event delegation and the benefit is that\n  // the Delete button of newly-added tasks will also respond\n  // to clicks without you having to manually add event listeners\n  // to them. You also don't have to remove any event listeners\n  // when the task is removed.\n  $todoListEl.addEventListener('click', (event) => {\n    // Check that the button is being clicked and not something\n    // else (e.g. the task label).\n    if (event.target.tagName === 'BUTTON') {\n      deleteTask(event.target.parentNode);\n    }\n  });\n})();\n\n\n"
        }
      ],
      "solutionReactFiles": [
        {
          "name": "public/index.html",
          "language": "html",
          "content": "<!DOCTYPE html>\n  <html>\n  <head>\n    <title>React App</title>\n  </head>\n  <body>\n    <div id=\"root\"></div>\n  </body>\n  </html>"
        },
        {
          "name": "src/App.js",
          "language": "javascript",
          "content": "let id = 0;\n\nconst INITIAL_TASKS = [\n  { id: id++, label: 'Walk the dog' },\n  { id: id++, label: 'Water the plants' },\n  { id: id++, label: 'Wash the dishes' },\n];\n\nfunction App() {\n  const [tasks, setTasks] = useState(INITIAL_TASKS);\n  const [newTask, setNewTask] = useState('');\n\n  return (\n    <div>\n      <h1>Todo List</h1>\n      <div>\n        <input\n          aria-label=\"Add new task\"\n          type=\"text\"\n          placeholder=\"Add your task\"\n          value={newTask}\n          onChange={(event) => {\n            setNewTask(event.target.value);\n          }}\n        />\n        <div>\n          <button\n            onClick={() => {\n              setTasks(\n                tasks.concat({\n                  id: id++,\n                  label: newTask.trim(),\n                }),\n              );\n              setNewTask('');\n            }}>\n            Submit\n          </button>\n        </div>\n      </div>\n      <ul>\n        {tasks.map(({ id, label }) => (\n          <li key={id}>\n            <span>{label}</span>\n            <button\n              onClick={() => {\n                setTasks(\n                  tasks.filter((task) => task.id !== id),\n                );\n              }}>\n              Delete\n            </button>\n          </li>\n        ))}\n      </ul>\n    </div>\n  );\n}\n\n\n"
        },
        {
          "name": "src/index.js",
          "language": "javascript",
          "content": "const root = ReactDOM.createRoot(document.getElementById('root'));\n  root.render(\n    <React.StrictMode>\n      <App />\n    </React.StrictMode>\n  );"
        },
        {
          "name": "src/style.css",
          "language": "css",
          "content": "body {\n  font-family: sans-serif;\n}\n\n"
        }
      ],
      "questionDetails": {
        "name": "Todo List",
        "questionaerInfo": {
          "name": "YanghSun Tay",
          "profilePic": "https://media.licdn.com/dms/image/v2/D5603AQFB72zuIqxYrQ/profile-displayphoto-shrink_400_400/profile-displayphoto-shrink_400_400/0/1684230919345?e=1744848000&v=beta&t=k1XZNF3EGY4g8MbqRfgp6bGPxWYQdH5_9cRp73CWgu0",
          "additionalInfo": "Ex-Meta Staff Engineer"
        },
        "techStack": ["html", "js", "react"],
        "difficulty": "Medium",
        "time": 20,
        "questionDescription": "You're given some existing HTML for a Todo List app. Add the following functionality to the app:\n\nAdd new tasks on clicking the \"Submit\" button, \nThe <input> field should be cleared upon successful addition, \nRemove tasks from the Todo List upon clicking the \"Delete\" button.",
        "requirements": [],
        "notes": [
          "The focus of this question is on functionality, not the styling. There's no need to write any custom CSS.",
          "You may modify the markup (e.g. adding ids, data attributes, replacing some tags, etc), but the result should remain the same visually.",
          "You may want to think about ways to improve the user experience of the application and implement them (you get bonus credit for doing that during interviews)."
        ],
        "companies": ["Apple", "Microsoft", "Twitter"],
        "questionType": "ui"
      }
    }
```

## 2. Logical Question Example: Find Max Consecutive ones 

```json
{
      "initialVanillaFiles": [
        {
          "name": "solution.js",
          "language": "javascript",
          "content": "// Please write your logic inside this function\nfunction findMaxConsecutiveOnes(nums) {\n\n}"
        }
      ],
      "initialReactFiles": [],
      "solutionVanillaFiles": [
        {
          "name": "solution.js",
          "language": "javascript",
          "content": "function findMaxConsecutiveOnes(nums) {\n  let maxCount = 0;\n  let currentCount = 0;\n\n  for (let num of nums) {\n    if (num === 1) {\n      currentCount++;\n      maxCount = Math.max(maxCount, currentCount);\n    } else {\n      currentCount = 0;\n    }\n  }\n\n  return maxCount;\n}"
        }
      ],
      "solutionReactFiles": [],
      "questionDetails": {
        "name": "Max Consecutive Ones",
        "questionaerInfo": {
          "name": "YanghSun Tay",
          "profilePic": "https://media.licdn.com/dms/image/v2/D5603AQFB72zuIqxYrQ/profile-displayphoto-shrink_400_400/profile-displayphoto-shrink_400_400/0/1684230919345?e=1744848000&v=beta&t=k1XZNF3EGY4g8MbqRfgp6bGPxWYQdH5_9cRp73CWgu0",
          "additionalInfo": "Ex-Meta Staff Engineer"
        },
        "techStack": ["js"],
        "difficulty": "Easy",
        "time": 20,
        "questionDescription": "Given a binary array `nums`, return the maximum number of consecutive 1's in the array. For example, if `nums = [1,1,0,1,1,1]`, the output should be 3 because the longest sequence of 1s is of length 3.",
        "requirements": [
          "Write a function `findMaxConsecutiveOnes` that takes an array of numbers (containing only 0s and 1s) as input.",
          "The function should return the length of the longest sequence of consecutive 1s."
        ],
        "notes": [
          "The input array will only contain 0s and 1s.",
          "The array length can be from 0 to 10^4.",
          "You can assume the input is valid (no need to handle edge cases like non-binary values)."
        ],
        "companies": ["Google", "Microsoft", "Facebook", "Netflix"],
        "questionType": "logical",
        "testCases": [
          {
            "input": "[1,1,0,1,1,1]",
            "output": 3,
            "description": "Test case with multiple sequences of 1s, longest is 3."
          },
          {
            "input": "[1,0,1,1,0,1]",
            "output": 2,
            "description": "Test case with alternating 0s and 1s, longest sequence is 2."
          },
          {
            "input": "[0,0,0]",
            "output": 0,
            "description": "Test case with no 1s."
          },
          {
            "input": "[1,1,1,1,1]",
            "output": 5,
            "description": "Test case with all 1s."
          },
          {
            "input": "[]",
            "output": 0,
            "description": "Test case with empty array."
          }
        ]
      }
    }
```

Key Differences Between UI and Logical Questions:

1. **File Structure**:
   - UI questions typically have multiple files (HTML, CSS, JS)
   - Logical questions usually have a single JavaScript file

2. **Test Cases**:
   - Only logical questions have structured test cases
   - UI questions are tested through user interaction

3. **Requirements**:
   - UI questions focus on user experience and interaction
   - Logical questions focus on algorithm correctness and efficiency

4. **Tech Stack**:
   - UI questions often use multiple technologies
   - Logical questions typically use only JavaScript

