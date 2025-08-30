# Brain.js සම්පූර්ණ Learning Roadmap - සිංහලෙන්
## මූලික තත්ත්වයේ සිට උසස් මට්ටම දක්වා

---

## 📚 Table of Contents
1. [Brain.js හැඳින්වීම](#1-brainjs-හැඳින්වීම)
2. [Installation සහ Setup](#2-installation-සහ-setup)
3. [මූලික සංකල්ප](#3-මූලික-සංකල්ප)
4. [සරල Projects](#4-සරල-projects)
5. [උසස් සංකල්ප](#5-උසස්-සංකල්ප)
6. [Full Stack Project](#6-full-stack-project)
7. [Tips සහ Best Practices](#7-tips-සහ-best-practices)

---

## 1. Brain.js හැඳින්වීම

### 🧠 Brain.js කියන්නේ මොකද්ද?

Brain.js කියන්නේ JavaScript වලින් Neural Networks සාදන්න පුළුවන් library එකක්. මෙය browser එකේත්, Node.js එකේත් run කරන්න පුළුවන්.

**මූලික වශයෙන්:**
- JavaScript වලින් Artificial Intelligence models සාදන්න පුළුවන්
- Machine Learning algorithms implement කරන්න පුළුවන්
- Web applications වලට intelligence add කරන්න පුළුවන්

### 🔄 Brain.js vs TensorFlow.js වෙනස

| විශේෂාංගය | Brain.js | TensorFlow.js |
|---------|----------|---------------|
| **ඉගෙන ගන්න පහසුකම** | ඉතාම පහසු | අපහසු |
| **කේත ප්‍රමාණය** | කුඩා | විශාල |
| **Performance** | මධ්‍යම මට්ටම | ඉතා වේගවත් |
| **Features** | මූලික Neural Networks | සියලුම AI Models |
| **Beginner Friendly** | ✅ | ❌ |

### 🧠 Neural Networks කියන්නේ මොකද්ද? (සරල වැදීම)

**Neural Network** කියන්නේ මිනිස් මොළයේ neurons (නියුරෝන) වල ක්‍රියාකාරිත්වය අනුකරණය කරන computer system එකක්.

**සරල උදාහරණය:**
```
Input (ආදානය) → Hidden Layer (සැඟවුණු ස්තරය) → Output (ප්‍රතිදානය)

උදා: වයස, උස → Neural Network → බර predict කරනවා
```

**Neural Network වල කොටස්:**
- **Neurons (නියුරෝන):** තොරතුරු process කරන කුඩා units
- **Layers (ස්තර):** neurons වල සමූහ
- **Weights (බර):** connections වල වැදගත්කම
- **Training (පුහුණු කිරීම):** data වලින් ඉගෙන ගන්නවා

---

## 2. Installation සහ Setup

### 📦 Node.js Setup

**Step 1: Node.js Download කරන්න**
```bash
# nodejs.org වෙතින් latest version download කරන්න
# Windows: .msi file
# Mac: .pkg file
# Linux: package manager use කරන්න
```

**Step 2: Installation Verify කරන්න**
```bash
node --version
npm --version
```

### 🚀 Brain.js Installation

**Step 3: New Project එකක් Start කරන්න**
```bash
mkdir my-brainjs-project
cd my-brainjs-project
npm init -y
```

**Step 4: Brain.js Install කරන්න**
```bash
npm install brain.js
```

**Step 5: Test File එකක් සාදන්න**
```javascript
// test.js file එකක් සාදන්න

const brain = require('brain.js');

console.log("Brain.js successfully installed!");
console.log("Version:", require('brain.js/package.json').version);

// Simple test
const network = new brain.NeuralNetwork();
console.log("Neural Network created successfully!");
```

**Step 6: Run කරන්න**
```bash
node test.js
```

---

## 3. මූලික සංකල්ප

### 📊 Data Structures in Brain.js

**Input Data Format:**
```javascript
// Object format (වස්තු ආකාරය)
const trainingData = [
  { input: [0, 0], output: [0] },
  { input: [0, 1], output: [1] },
  { input: [1, 0], output: [1] },
  { input: [1, 1], output: [0] }
];

// Text format (පාඨ ආකාරය) - NLP සඳහා
const textData = [
  { input: "ආයුබෝවන්", output: "hello" },
  { input: "සුභ දවසක්", output: "good day" }
];
```

### 🎯 Neural Network Types

**1. NeuralNetwork - සාමාන්‍ය network**
```javascript
const brain = require('brain.js');
const network = new brain.NeuralNetwork();
```

**2. LSTM - Text/Sequence processing**
```javascript
const lstm = new brain.LSTM();
```

**3. RNN - Recurrent Neural Network**
```javascript
const rnn = new brain.recurrent.LSTM();
```

### 🔧 Basic Training Process

```javascript
// 1. Data prepare කරන්න
const trainingData = [
  { input: [0, 0], output: [0] },
  { input: [1, 1], output: [1] }
];

// 2. Network එක create කරන්න
const network = new brain.NeuralNetwork();

// 3. Train කරන්න
network.train(trainingData);

// 4. Test කරන්න
const result = network.run([1, 0]);
console.log("Prediction:", result);
```

---

## 4. සරල Projects

### 🔢 Project 1: XOR Problem

**XOR කියන්නේ මොකද්ද?**
XOR (Exclusive OR) කියන්නේ logic gate එකක්. එකම values නම් 0, වෙනස් values නම් 1.

```javascript
// xor-project.js
const brain = require('brain.js');

// XOR training data
const trainingData = [
  { input: [0, 0], output: [0] },  // 0 XOR 0 = 0
  { input: [0, 1], output: [1] },  // 0 XOR 1 = 1
  { input: [1, 0], output: [1] },  // 1 XOR 0 = 1
  { input: [1, 1], output: [0] }   // 1 XOR 1 = 0
];

console.log("🧠 XOR Neural Network Training ආරම්භ වෙනවා...");

// Neural Network එක create කරන්න
const network = new brain.NeuralNetwork({
  hiddenLayers: [3], // hidden layer එකේ neurons 3ක්
  learningRate: 0.3   // ඉගෙන ගන්න වේගය
});

// Training කරන්න
const stats = network.train(trainingData, {
  iterations: 20000,    // පුනරාවර්තන ගණන
  log: true,           // progress show කරන්න
  logPeriod: 1000      // හර 1000කට වරක් log කරන්න
});

console.log("✅ Training සම්පූර්ණයි!");
console.log("Training Stats:", stats);

// Test කරන්න
console.log("\n🧪 Testing Results:");
console.log("0 XOR 0 =", network.run([0, 0])[0].toFixed(4));
console.log("0 XOR 1 =", network.run([0, 1])[0].toFixed(4));
console.log("1 XOR 0 =", network.run([1, 0])[0].toFixed(4));
console.log("1 XOR 1 =", network.run([1, 1])[0].toFixed(4));
```

**Output:**
```
🧠 XOR Neural Network Training ආරම්භ වෙනවා...
iterations: 1000, training error: 0.247...
iterations: 2000, training error: 0.124...
✅ Training සම්පූර්ණයි!

🧪 Testing Results:
0 XOR 0 = 0.0123
0 XOR 1 = 0.9876
1 XOR 0 = 0.9823
1 XOR 1 = 0.0234
```

### 🤖 Project 2: සරල FAQ Chatbot

```javascript
// faq-chatbot.js
const brain = require('brain.js');

// FAQ training data
const trainingData = [
  // ආයුබෝවන් / Hello
  { input: "ආයුබෝවන්", output: "greeting" },
  { input: "හලෝ", output: "greeting" },
  { input: "සුභ දවසක්", output: "greeting" },
  
  // නම / Name
  { input: "ඔයාගේ නම මොකද්ද", output: "name" },
  { input: "ඔබේ නම", output: "name" },
  
  // උදව් / Help
  { input: "උදව්", output: "help" },
  { input: "මට උදව් කරන්න", output: "help" },
  
  // ගුඩ්බයි / Goodbye
  { input: "බායි", output: "goodbye" },
  { input: "ගුඩ්බයි", output: "goodbye" }
];

// Text වල characters වලට numbers convert කරන function
function textToNumbers(text) {
  const numbers = [];
  for (let i = 0; i < text.length; i++) {
    numbers.push(text.charCodeAt(i) / 255); // normalize කරන්න
  }
  // Fixed length arrays සඳහා padding
  while (numbers.length < 50) {
    numbers.push(0);
  }
  return numbers.slice(0, 50); // maximum 50 characters
}

// Response categories
const responses = {
  greeting: ["ආයුබෝවන්! මට ඔබට උදව් කරන්න පුළුවන්.", "හලෝ! කෙහොමද?", "සුභ දවසක්!"],
  name: ["මගේ නම AI Assistant. මම Brain.js වලින් සාදා ගත්තා.", "මම ඔබේ AI මිතුරා!"],
  help: ["මට ඔබට ප්‍රශ්න වලට උත්තර දෙන්න පුළුවන්. කුමක් දැනගන්න ඕන?", "මම මෙතන ඔබට උදව් කරන්න!"],
  goodbye: ["ගුඩ්බයි! හොඳ දවසක් වේවා!", "බායි! නැවතත් එන්න!"]
};

// Training data format කරන්න
const formattedTrainingData = trainingData.map(item => ({
  input: textToNumbers(item.input),
  output: { [item.output]: 1 }
}));

console.log("🤖 Chatbot Training ආරම්භ වෙනවා...");

const network = new brain.NeuralNetwork({
  hiddenLayers: [20, 20],
  learningRate: 0.1
});

network.train(formattedTrainingData, {
  iterations: 10000,
  log: true,
  logPeriod: 1000
});

console.log("✅ Chatbot Training සම්පූර්ණයි!");

// Chat function
function chat(userInput) {
  const prediction = network.run(textToNumbers(userInput));
  
  // Highest probability category find කරන්න
  let bestCategory = null;
  let bestScore = 0;
  
  for (const category in prediction) {
    if (prediction[category] > bestScore) {
      bestScore = prediction[category];
      bestCategory = category;
    }
  }
  
  // Response එක return කරන්න
  if (bestScore > 0.5 && responses[bestCategory]) {
    const categoryResponses = responses[bestCategory];
    return categoryResponses[Math.floor(Math.random() * categoryResponses.length)];
  } else {
    return "මට ඒක තේරුණේ නැහැ. වෙන විදියකට ප්‍රශ්නය අහන්න පුළුවන්ද?";
  }
}

// Test conversations
console.log("\n💬 Chatbot Testing:");
console.log("User: ආයුබෝවන්");
console.log("Bot:", chat("ආයුබෝවන්"));

console.log("\nUser: ඔයාගේ නම මොකද්ද");
console.log("Bot:", chat("ඔයාගේ නම මොකද්ද"));

console.log("\nUser: උදව්");
console.log("Bot:", chat("උදව්"));

console.log("\nUser: බායි");
console.log("Bot:", chat("බායි"));
```

### 📈 Project 3: Number Prediction (Regression)

```javascript
// number-prediction.js
const brain = require('brain.js');

// උදාහරණ: salary prediction based on experience
const trainingData = [
  { input: [1], output: [30000] },   // 1 year = 30k
  { input: [2], output: [35000] },   // 2 years = 35k
  { input: [3], output: [42000] },   // 3 years = 42k
  { input: [4], output: [50000] },   // 4 years = 50k
  { input: [5], output: [58000] },   // 5 years = 58k
  { input: [6], output: [65000] },   // 6 years = 65k
  { input: [7], output: [72000] },   // 7 years = 72k
  { input: [8], output: [80000] },   // 8 years = 80k
  { input: [9], output: [88000] },   // 9 years = 88k
  { input: [10], output: [95000] }   // 10 years = 95k
];

// Data normalize කරන්න (0-1 range එකට convert කරන්න)
function normalizeInput(years) {
  return years / 15; // maximum 15 years assume කරන්න
}

function normalizeOutput(salary) {
  return salary / 120000; // maximum 120k assume කරන්න
}

function denormalizeSalary(normalizedSalary) {
  return normalizedSalary * 120000;
}

// Normalized training data
const normalizedTrainingData = trainingData.map(item => ({
  input: [normalizeInput(item.input[0])],
  output: [normalizeOutput(item.output[0])]
}));

console.log("💰 Salary Prediction Model Training ආරම්භ වෙනවා...");

const network = new brain.NeuralNetwork({
  hiddenLayers: [10, 8],
  learningRate: 0.3
});

network.train(normalizedTrainingData, {
  iterations: 50000,
  log: true,
  logPeriod: 5000,
  errorThresh: 0.005
});

console.log("✅ Training සම්පූර්ණයි!");

// Prediction function
function predictSalary(years) {
  const normalizedInput = normalizeInput(years);
  const normalizedPrediction = network.run([normalizedInput]);
  return denormalizeSalary(normalizedPrediction[0]);
}

// Test predictions
console.log("\n📊 Salary Predictions:");
console.log(`3.5 years experience: $${predictSalary(3.5).toFixed(0)}`);
console.log(`6.5 years experience: $${predictSalary(6.5).toFixed(0)}`);
console.log(`12 years experience: $${predictSalary(12).toFixed(0)}`);
console.log(`15 years experience: $${predictSalary(15).toFixed(0)}`);

// Accuracy test
console.log("\n🎯 Accuracy Test:");
trainingData.forEach(item => {
  const predicted = predictSalary(item.input[0]);
  const actual = item.output[0];
  const accuracy = (1 - Math.abs(predicted - actual) / actual) * 100;
  console.log(`${item.input[0]} years: Actual=$${actual}, Predicted=$${predicted.toFixed(0)}, Accuracy=${accuracy.toFixed(1)}%`);
});
```

### 🎮 Project 4: Simple Game AI (Tic Tac Toe)

```javascript
// tic-tac-toe-ai.js
const brain = require('brain.js');

// Tic Tac Toe board positions:
// 0 | 1 | 2
// ---------
// 3 | 4 | 5
// ---------
// 6 | 7 | 8

// Training data - winning moves
const trainingData = [
  // Winning patterns
  { input: [1, 1, 0, 0, 0, 0, 0, 0, 0], output: [0, 0, 1, 0, 0, 0, 0, 0, 0] }, // Complete row
  { input: [1, 0, 1, 0, 0, 0, 0, 0, 0], output: [0, 1, 0, 0, 0, 0, 0, 0, 0] }, // Complete row
  { input: [0, 1, 1, 0, 0, 0, 0, 0, 0], output: [1, 0, 0, 0, 0, 0, 0, 0, 0] }, // Complete row
  
  // Blocking opponent
  { input: [-1, -1, 0, 0, 0, 0, 0, 0, 0], output: [0, 0, 1, 0, 0, 0, 0, 0, 0] }, // Block opponent
  { input: [-1, 0, -1, 0, 0, 0, 0, 0, 0], output: [0, 1, 0, 0, 0, 0, 0, 0, 0] }, // Block opponent
  
  // Center strategy
  { input: [0, 0, 0, 0, 0, 0, 0, 0, 0], output: [0, 0, 0, 0, 1, 0, 0, 0, 0] }, // Take center
  
  // Corner strategy
  { input: [-1, 0, 0, 0, 1, 0, 0, 0, 0], output: [0, 0, 1, 0, 0, 0, 0, 0, 0] }, // Take corner
];

console.log("🎮 Tic Tac Toe AI Training ආරම්භ වෙනවා...");

const network = new brain.NeuralNetwork({
  hiddenLayers: [18, 12],
  learningRate: 0.3
});

network.train(trainingData, {
  iterations: 20000,
  log: true,
  logPeriod: 2000
});

console.log("✅ AI Training සම්පූර්ණයි!");

// Game functions
function displayBoard(board) {
  const symbols = { 1: 'X', '-1': 'O', 0: ' ' };
  console.log(`
 ${symbols[board[0]]} | ${symbols[board[1]]} | ${symbols[board[2]]} 
-----------
 ${symbols[board[3]]} | ${symbols[board[4]]} | ${symbols[board[5]]} 
-----------
 ${symbols[board[6]]} | ${symbols[board[7]]} | ${symbols[board[8]]} 
`);
}

function checkWinner(board) {
  const winPatterns = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8], // rows
    [0, 3, 6], [1, 4, 7], [2, 5, 8], // columns
    [0, 4, 8], [2, 4, 6] // diagonals
  ];
  
  for (const pattern of winPatterns) {
    const [a, b, c] = pattern;
    if (board[a] !== 0 && board[a] === board[b] && board[b] === board[c]) {
      return board[a];
    }
  }
  return board.includes(0) ? null : 'tie';
}

function aiMove(board) {
  const prediction = network.run(board);
  
  // හැකි moves වලින් highest probability එක select කරන්න
  let bestMove = -1;
  let bestScore = -1;
  
  for (let i = 0; i < 9; i++) {
    if (board[i] === 0 && prediction[i] > bestScore) {
      bestScore = prediction[i];
      bestMove = i;
    }
  }
  
  // AI move එක empty space එකක් නම් return කරන්න
  if (bestMove !== -1 && board[bestMove] === 0) {
    return bestMove;
  }
  
  // Random fallback
  const emptySpaces = board.map((cell, index) => cell === 0 ? index : -1).filter(x => x !== -1);
  return emptySpaces[Math.floor(Math.random() * emptySpaces.length)];
}

// Game simulation
function playGame() {
  let board = [0, 0, 0, 0, 0, 0, 0, 0, 0];
  let currentPlayer = 1; // 1 = Human (X), -1 = AI (O)
  
  console.log("🎮 New Game Started! ඔබ X, AI O");
  displayBoard(board);
  
  while (true) {
    if (currentPlayer === 1) {
      // Human move (random for demo)
      const emptySpaces = board.map((cell, index) => cell === 0 ? index : -1).filter(x => x !== -1);
      if (emptySpaces.length === 0) break;
      
      const humanMove = emptySpaces[Math.floor(Math.random() * emptySpaces.length)];
      board[humanMove] = 1;
      console.log(`Human plays position ${humanMove}`);
    } else {
      // AI move
      const aiMovePos = aiMove(board);
      if (aiMovePos !== -1) {
        board[aiMovePos] = -1;
        console.log(`AI plays position ${aiMovePos}`);
      }
    }
    
    displayBoard(board);
    
    const winner = checkWinner(board);
    if (winner !== null) {
      if (winner === 1) console.log("🏆 Human Wins!");
      else if (winner === -1) console.log("🤖 AI Wins!");
      else console.log("🤝 It's a Tie!");
      break;
    }
    
    currentPlayer *= -1; // Switch player
  }
}

// Play a demo game
playGame();
```

---

## 5. උසස් සංකල්ප

### 🔄 LSTM Networks (Long Short-Term Memory)

LSTM networks text generation සහ sequence prediction සඳහා use කරනවා.

```javascript
// lstm-text-generation.js
const brain = require('brain.js');

// Text generation using LSTM
const texts = [
  'hello world',
  'brain js is awesome',
  'neural networks are cool',
  'machine learning with javascript',
  'artificial intelligence rocks'
];

console.log("📝 LSTM Text Generation Training ආරම්භ වෙනවා...");

const lstm = new brain.recurrent.LSTM({
  inputSize: 20,
  hiddenLayers: [20, 20],
  outputSize: 20
});

// Train the LSTM
lstm.train(texts, {
  iterations: 2000,
  log: true,
  logPeriod: 100
});

console.log("✅ LSTM Training සම්පූර්ණයි!");

// Generate text
console.log("\n🎨 Generated Text:");
console.log(lstm.run('hello'));
console.log(lstm.run('brain'));
console.log(lstm.run('neural'));
```

### ⚙️ Training Parameters විස්තර

```javascript
// advanced-training-params.js
const brain = require('brain.js');

const network = new brain.NeuralNetwork({
  // Network architecture
  inputSize: 2,
  hiddenLayers: [10, 8, 6], // Multiple hidden layers
  outputSize: 1,
  
  // Learning parameters
  learningRate: 0.3,        // ඉගෙන ගන්න වේගය (0.01 - 0.9)
  momentum: 0.1,            // Previous updates influence (0 - 1)
  
  // Activation functions
  activation: 'sigmoid',     // sigmoid, tanh, relu
  leakyReluAlpha: 0.01      // For leaky ReLU activation
});

const trainingData = [
  { input: [0, 0], output: [0] },
  { input: [0, 1], output: [1] },
  { input: [1, 0], output: [1] },
  { input: [1, 1], output: [0] }
];

// Advanced training options
const trainingOptions = {
  iterations: 50000,         // Maximum iterations
  errorThresh: 0.005,        // Target error threshold
  log: true,                 // Show progress
  logPeriod: 1000,          // Log frequency
  learningRate: 0.3,        // Override network learning rate
  momentum: 0.1,            // Momentum factor
  callback: null,           // Custom callback function
  callbackPeriod: 1000,     // Callback frequency
  timeout: Infinity         // Training timeout (ms)
};

console.log("🔧 Advanced Training with Custom Parameters...");

const stats = network.train(trainingData, trainingOptions);

console.log("Training Statistics:", {
  error: stats.error,
  iterations: stats.iterations
});

// Test with confidence scores
function testWithConfidence(input) {
  const result = network.run(input);
  const confidence = Math.max(...result);
  
  console.log(`Input: [${input.join(', ')}]`);
  console.log(`Output: ${result[0].toFixed(4)}`);
  console.log(`Confidence: ${(confidence * 100).toFixed(2)}%`);
}

console.log("\n🧪 Testing with Confidence:");
testWithConfidence([0, 0]);
testWithConfidence([1, 1]);
```

### 💾 Model Save සහ Load කිරීම

```javascript
// model-save-load.js
const brain = require('brain.js');
const fs = require('fs');

// Create and train a model
const network = new brain.NeuralNetwork();
const trainingData = [
  { input: [0, 0], output: [0] },
  { input: [0, 1], output: [1] },
  { input: [1, 0], output: [1] },
  { input: [1, 1], output: [0] }
];

console.log("🏋️ Training model...");
network.train(trainingData, { iterations: 20000 });

// Save model to JSON
const modelData = network.toJSON();
fs.writeFileSync('xor-model.json', JSON.stringify(modelData, null, 2));
console.log("💾 Model saved to xor-model.json");

// Save as executable function
const modelFunction = network.toFunction();
const functionCode = `const xorPredictor = ${modelFunction.toString()};
module.exports = xorPredictor;`;
fs.writeFileSync('xor-predictor.js', functionCode);
console.log("🔧 Model saved as executable function");

// Load model from JSON
function loadModel() {
  const savedModel = JSON.parse(fs.readFileSync('xor-model.json', 'utf8'));
  const newNetwork = new brain.NeuralNetwork();
  newNetwork.fromJSON(savedModel);
  return newNetwork;
}

// Test loaded model
console.log("\n📂 Loading and testing saved model...");
const loadedNetwork = loadModel();
console.log("Loaded model result for [1, 0]:", loadedNetwork.run([1, 0]));

// Use executable function
const xorPredictor = require('./xor-predictor.js');
console.log("Function predictor result for [1, 0]:", xorPredictor([1, 0]));
```

### 🔧 Error Handling සහ Debugging

```javascript
// error-handling-debugging.js
const brain = require('brain.js');

class NeuralNetworkManager {
  constructor(options = {}) {
    this.network = null;
    this.trainingData = [];
    this.isTrained = false;
    this.options = {
      hiddenLayers: [3],
      learningRate: 0.3,
      ...options
    };
  }

  // Data validation
  validateData(data) {
    const errors = [];
    
    if (!Array.isArray(data) || data.length === 0) {
      errors.push("Training data array එක empty හෝ invalid");
    }
    
    data.forEach((item, index) => {
      if (!item.input || !item.output) {
        errors.push(`Item ${index}: input හෝ output නැත`);
      }
      
      if (!Array.isArray(item.input) || !Array.isArray(item.output)) {
        errors.push(`Item ${index}: input සහ output arrays විය යුතුයි`);
      }
    });
    
    return errors;
  }

  // Safe training with error handling
  train(data, options = {}) {
    try {
      console.log("🔍 Data validation කරනවා...");
      
      // Validate data
      const validationErrors = this.validateData(data);
      if (validationErrors.length > 0) {
        throw new Error("Data validation failed:\n" + validationErrors.join("\n"));
      }
      
      console.log("✅ Data validation සාර්ථකයි");
      
      // Create network
      this.network = new brain.NeuralNetwork(this.options);
      
      // Training options with error handling
      const trainingOptions = {
        iterations: 20000,
        errorThresh: 0.005,
        log: true,
        logPeriod: 1000,
        callback: (stats) => {
          // Custom callback for monitoring
          if (stats.iterations % 5000 === 0) {
            console.log(`📊 Progress: ${stats.iterations} iterations, Error: ${stats.error.toFixed(6)}`);
          }
          
          // Stop if error is too high after many iterations
          if (stats.iterations > 50000 && stats.error > 0.1) {
            console.log("⚠️ Warning: High error after many iterations");
            return true; // Stop training
          }
        },
        ...options
      };
      
      console.log("🏋️ Training ආරම්භ කරනවා...");
      const stats = this.network.train(data, trainingOptions);
      
      this.isTrained = true;
      this.trainingData = data;
      
      console.log("✅ Training සම්පූර්ණයි!");
      console.log(`📈 Final Error: ${stats.error.toFixed(6)}`);
      console.log(`🔄 Iterations: ${stats.iterations}`);
      
      return stats;
      
    } catch (error) {
      console.error("❌ Training Error:", error.message);
      this.isTrained = false;
      throw error;
    }
  }

  // Safe prediction with error handling
  predict(input) {
    try {
      if (!this.isTrained) {
        throw new Error("Model තවම train කරා නැත");
      }
      
      if (!Array.isArray(input)) {
        throw new Error("Input array එකක් විය යුතුයි");
      }
      
      const result = this.network.run(input);
      
      // Check for invalid results
      if (result.some(val => isNaN(val) || !isFinite(val))) {
        throw new Error("Invalid prediction result");
      }
      
      return {
        prediction: result,
        confidence: this.calculateConfidence(result),
        input: input
      };
      
    } catch (error) {
      console.error("❌ Prediction Error:", error.message);
      return null;
    }
  }
  
  // Calculate prediction confidence
  calculateConfidence(result) {
    const maxValue = Math.max(...result);
    const minValue = Math.min(...result);
    return ((maxValue - minValue) * 100).toFixed(2) + '%';
  }
  
  // Model diagnostics
  diagnose() {
    if (!this.isTrained) {
      console.log("❌ Model trained නැත");
      return;
    }
    
    console.log("🔬 Model Diagnostics:");
    console.log("Network Structure:", this.options);
    console.log("Training Data Size:", this.trainingData.length);
    console.log("Is Trained:", this.isTrained);
    
    // Test with training data
    console.log("\n📊 Training Data Performance:");
    this.trainingData.forEach((item, index) => {
      const prediction = this.predict(item.input);
      if (prediction) {
        const error = this.calculateError(item.output, prediction.prediction);
        console.log(`Sample ${index}: Error ${error.toFixed(4)}, Confidence ${prediction.confidence}`);
      }
    });
  }
  
  // Calculate error between expected and predicted
  calculateError(expected, predicted) {
    let totalError = 0;
    for (let i = 0; i < expected.length; i++) {
      totalError += Math.pow(expected[i] - predicted[i], 2);
    }
    return Math.sqrt(totalError / expected.length);
  }
}

// Usage example with error handling
console.log("🧠 Neural Network with Error Handling");

const networkManager = new NeuralNetworkManager({
  hiddenLayers: [4, 3],
  learningRate: 0.3
});

// Test data - XOR problem
const trainingData = [
  { input: [0, 0], output: [0] },
  { input: [0, 1], output: [1] },
  { input: [1, 0], output: [1] },
  { input: [1, 1], output: [0] }
];

// Train with error handling
try {
  const stats = networkManager.train(trainingData);
  
  // Test predictions
  console.log("\n🧪 Testing Predictions:");
  const testInputs = [[0, 0], [0, 1], [1, 0], [1, 1], [0.5, 0.5]];
  
  testInputs.forEach(input => {
    const result = networkManager.predict(input);
    if (result) {
      console.log(`Input: [${input.join(', ')}] → Prediction: ${result.prediction[0].toFixed(4)} (${result.confidence})`);
    }
  });
  
  // Run diagnostics
  networkManager.diagnose();
  
} catch (error) {
  console.error("Training failed:", error.message);
}

// Test error scenarios
console.log("\n🚨 Testing Error Scenarios:");

// Invalid data test
try {
  networkManager.train([{ input: "invalid" }]);
} catch (error) {
  console.log("Caught expected error:", error.message);
}

// Prediction without training
const newManager = new NeuralNetworkManager();
const invalidPrediction = newManager.predict([1, 0]);
console.log("Invalid prediction result:", invalidPrediction);
```

---

## 6. Full Stack Project

### 🌐 Complete Web Application with Brain.js

මේ project එකේ අපි chatbot එකක් සාදන්නම් HTML frontend, Node.js backend සහ database integration සමග.

#### Backend - Node.js Server

```javascript
// server.js
const express = require('express');
const brain = require('brain.js');
const path = require('path');
const fs = require('fs');

const app = express();
const PORT = 3000;

// Middleware
app.use(express.json());
app.use(express.static('public'));

// Global variables
let chatbot = null;
let isTraining = false;

// Training data for chatbot
const trainingData = [
  // Greetings - ආයුබෝවන්
  { input: "hello", output: { greeting: 1 } },
  { input: "hi", output: { greeting: 1 } },
  { input: "ayubowan", output: { greeting: 1 } },
  { input: "good morning", output: { greeting: 1 } },
  
  // Questions - ප්‍රශ්න
  { input: "how are you", output: { how_are_you: 1 } },
  { input: "what is your name", output: { name: 1 } },
  { input: "who are you", output: { name: 1 } },
  
  // Help - උදව්
  { input: "help", output: { help: 1 } },
  { input: "what can you do", output: { help: 1 } },
  
  // Goodbye - සමුගැනීම
  { input: "bye", output: { goodbye: 1 } },
  { input: "goodbye", output: { goodbye: 1 } },
  { input: "see you later", output: { goodbye: 1 } },
  
  // Weather - කාලගුණය
  { input: "weather", output: { weather: 1 } },
  { input: "how is the weather", output: { weather: 1 } },
  
  // Time - කාලය
  { input: "time", output: { time: 1 } },
  { input: "what time is it", output: { time: 1 } }
];

// Response templates
const responses = {
  greeting: [
    "Hello! How can I help you today?",
    "Hi there! Welcome to our AI assistant!",
    "Ayubowan! I'm here to help you."
  ],
  how_are_you: [
    "I'm doing great! Thanks for asking. How are you?",
    "I'm fine and ready to help you!",
    "Everything is good! How can I assist you?"
  ],
  name: [
    "I'm your AI assistant powered by Brain.js!",
    "My name is BrainBot, your helpful AI companion.",
    "I'm an AI assistant created with Brain.js and Node.js!"
  ],
  help: [
    "I can help you with various questions! Try asking about weather, time, or just chat with me!",
    "I'm here to assist you! Ask me anything you'd like to know.",
    "You can ask me about weather, time, or just have a casual conversation!"
  ],
  goodbye: [
    "Goodbye! Have a great day!",
    "See you later! Take care!",
    "Bye! Come back anytime!"
  ],
  weather: [
    "I don't have access to real weather data, but I hope it's nice where you are!",
    "For accurate weather information, please check your local weather service.",
    "I wish I could tell you the weather! Try checking a weather website."
  ],
  time: [
    `The current time is ${new Date().toLocaleTimeString()}`,
    `Right now it's ${new Date().toLocaleTimeString()}`,
    `Current time: ${new Date().toLocaleTimeString()}`
  ],
  default: [
    "I'm not sure I understand. Could you try asking something else?",
    "Hmm, I don't quite get that. Can you rephrase your question?",
    "I'm still learning! Could you ask me something else?"
  ]
};

// Text processing functions
function preprocessText(text) {
  return text.toLowerCase()
    .replace(/[^\w\s]/gi, '') // Remove punctuation
    .trim();
}

function textToNumbers(text) {
  const numbers = [];
  const processedText = preprocessText(text);
  
  for (let i = 0; i < processedText.length; i++) {
    numbers.push(processedText.charCodeAt(i) / 255);
  }
  
  // Fixed length padding
  while (numbers.length < 50) {
    numbers.push(0);
  }
  
  return numbers.slice(0, 50);
}

// Initialize and train chatbot
async function initializeChatbot() {
  console.log("🤖 Initializing chatbot...");
  
  try {
    isTraining = true;
    
    // Check if trained model exists
    if (fs.existsSync('chatbot-model.json')) {
      console.log("📂 Loading existing model...");
      const modelData = JSON.parse(fs.readFileSync('chatbot-model.json', 'utf8'));
      chatbot = new brain.NeuralNetwork();
      chatbot.fromJSON(modelData);
      console.log("✅ Model loaded successfully!");
    } else {
      console.log("🏋️ Training new model...");
      
      // Format training data
      const formattedData = trainingData.map(item => ({
        input: textToNumbers(item.input),
        output: item.output
      }));
      
      chatbot = new brain.NeuralNetwork({
        hiddenLayers: [20, 16, 12],
        learningRate: 0.1
      });
      
      // Train the model
      const stats = chatbot.train(formattedData, {
        iterations: 15000,
        log: true,
        logPeriod: 1000,
        errorThresh: 0.01
      });
      
      // Save trained model
      fs.writeFileSync('chatbot-model.json', JSON.stringify(chatbot.toJSON(), null, 2));
      console.log("💾 Model saved!");
      console.log("✅ Training completed!", stats);
    }
    
    isTraining = false;
  } catch (error) {
    console.error("❌ Chatbot initialization failed:", error);
    isTraining = false;
  }
}

// Chat endpoint
app.post('/api/chat', (req, res) => {
  try {
    const { message } = req.body;
    
    if (isTraining) {
      return res.json({
        response: "I'm still learning... Please wait a moment!",
        confidence: 0,
        category: "training"
      });
    }
    
    if (!chatbot) {
      return res.json({
        response: "Sorry, I'm not ready yet. Please try again later.",
        confidence: 0,
        category: "error"
      });
    }
    
    // Get prediction
    const prediction = chatbot.run(textToNumbers(message));
    
    // Find best category
    let bestCategory = null;
    let bestScore = 0;
    
    for (const category in prediction) {
      if (prediction[category] > bestScore) {
        bestScore = prediction[category];
        bestCategory = category;
      }
    }
    
    // Generate response
    let responseText;
    if (bestScore > 0.4 && responses[bestCategory]) {
      const categoryResponses = responses[bestCategory];
      responseText = categoryResponses[Math.floor(Math.random() * categoryResponses.length)];
    } else {
      const defaultResponses = responses.default;
      responseText = defaultResponses[Math.floor(Math.random() * defaultResponses.length)];
      bestCategory = 'default';
    }
    
    res.json({
      response: responseText,
      confidence: (bestScore * 100).toFixed(1),
      category: bestCategory
    });
    
  } catch (error) {
    console.error("Chat error:", error);
    res.status(500).json({
      response: "Sorry, something went wrong!",
      confidence: 0,
      category: "error"
    });
  }
});

// Status endpoint
app.get('/api/status', (req, res) => {
  res.json({
    ready: !isTraining && chatbot !== null,
    training: isTraining,
    modelExists: fs.existsSync('chatbot-model.json')
  });
});

// Serve HTML page
app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, 'public', 'index.html'));
});

// Start server
app.listen(PORT, () => {
  console.log(`🚀 Server running on http://localhost:${PORT}`);
  initializeChatbot();
});
```

#### Frontend - HTML සහ JavaScript

```html
<!-- public/index.html -->
<!DOCTYPE html>
<html lang="si">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Brain.js Chatbot - සිංහල</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .chat-container {
            width: 90%;
            max-width: 500px;
            height: 80vh;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }
        
        .chat-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }
        
        .chat-header h1 {
            margin: 0;
            font-size: 1.5em;
        }
        
        .status {
            font-size: 0.9em;
            opacity: 0.9;
            margin-top: 5px;
        }
        
        .chat-messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .message {
            display: flex;
            gap: 10px;
            animation: fadeIn 0.3s ease-in;
        }
        
        .message.user {
            justify-content: flex-end;
        }
        
        .message-content {
            max-width: 70%;
            padding: 12px 16px;
            border-radius: 18px;
            word-wrap: break-word;
        }
        
        .message.bot .message-content {
            background: #f1f3f4;
            color: #333;
        }
        
        .message.user .message-content {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }
        
        .message-info {
            font-size: 0.7em;
            opacity: 0.7;
            margin-top: 5px;
        }
        
        .chat-input {
            padding: 20px;
            border-top: 1px solid #eee;
            display: flex;
            gap: 10px;
        }
        
        .chat-input input {
            flex: 1;
            padding: 12px 16px;
            border: 2px solid #eee;
            border-radius: 25px;
            font-size: 1em;
            outline: none;
            transition: border-color 0.3s;
        }
        
        .chat-input input:focus {
            border-color: #667eea;
        }
        
        .chat-input button {
            padding: 12px 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1em;
            font-weight: bold;
            transition: transform 0.2s;
        }
        
        .chat-input button:hover {
            transform: translateY(-2px);
        }
        
        .chat-input button:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
        }
        
        .loading {
            display: flex;
            gap: 4px;
            padding: 8px 16px;
        }
        
        .loading div {
            width: 8px;
            height: 8px;
            background: #667eea;
            border-radius: 50%;
            animation: loading 1.4s infinite ease-in-out both;
        }
        
        .loading div:nth-child(1) { animation-delay: -0.32s; }
        .loading div:nth-child(2) { animation-delay: -0.16s; }
        .loading div:nth-child(3) { animation-delay: 0s; }
        
        @keyframes loading {
            0%, 80%, 100% { 
                transform: scale(0);
                opacity: 0.5;
            } 
            40% { 
                transform: scale(1);
                opacity: 1;
            }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .example-questions {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 10px;
        }
        
        .example-btn {
            padding: 8px 12px;
            background: #f1f3f4;
            border: none;
            border-radius: 15px;
            cursor: pointer;
            font-size: 0.9em;
            transition: background 0.2s;
        }
        
        .example-btn:hover {
            background: #e8eaf6;
        }
        
        @media (max-width: 600px) {
            .chat-container {
                width: 100%;
                height: 100vh;
                border-radius: 0;
            }
        }
    </style>
</head>
<body>
    <div class="chat-container">
        <div class="chat-header">
            <h1>🧠 Brain.js AI Assistant</h1>
            <div class="status" id="status">Loading...</div>
        </div>
        
        <div class="chat-messages" id="chatMessages">
            <div class="message bot">
                <div class="message-content">
                    Hello! I'm your AI assistant powered by Brain.js. How can I help you today?
                    <div class="message-info">AI • Ready to chat</div>
                </div>
            </div>
        </div>
        
        <div class="chat-input">
            <div style="flex: 1;">
                <div class="example-questions">
                    <button class="example-btn" onclick="sendExample('Hello!')">Hello!</button>
                    <button class="example-btn" onclick="sendExample('How are you?')">How are you?</button>
                    <button class="example-btn" onclick="sendExample('What time is it?')">Time</button>
                    <button class="example-btn" onclick="sendExample('Help')">Help</button>
                </div>
                <input type="text" id="messageInput" placeholder="Type your message here..." />
            </div>
            <button onclick="sendMessage()" id="sendBtn">Send</button>
        </div>
    </div>

    <script>
        let isReady = false;
        let isWaiting = false;
        
        // DOM elements
        const chatMessages = document.getElementById('chatMessages');
        const messageInput = document.getElementById('messageInput');
        const sendBtn = document.getElementById('sendBtn');
        const statusDiv = document.getElementById('status');
        
        // Check server status
        async function checkStatus() {
            try {
                const response = await fetch('/api/status');
                const data = await response.json();
                
                isReady = data.ready;
                
                if (data.training) {
                    statusDiv.textContent = '🏋️ Training in progress...';
                } else if (data.ready) {
                    statusDiv.textContent = '✅ Ready to chat!';
                } else {
                    statusDiv.textContent = '⏳ Loading...';
                }
                
                updateUI();
            } catch (error) {
                statusDiv.textContent = '❌ Connection error';
                console.error('Status check failed:', error);
            }
        }
        
        // Update UI based on status
        function updateUI() {
            sendBtn.disabled = !isReady || isWaiting;
            messageInput.disabled = !isReady || isWaiting;
        }
        
        // Add message to chat
        function addMessage(content, isUser = false, info = '') {
            const messageDiv = document.createElement('div');
            messageDiv.className = `message ${isUser ? 'user' : 'bot'}`;
            
            const contentDiv = document.createElement('div');
            contentDiv.className = 'message-content';
            
            if (typeof content === 'string') {
                contentDiv.textContent = content;
            } else {
                contentDiv.appendChild(content);
            }
            
            if (info) {
                const infoDiv = document.createElement('div');
                infoDiv.className = 'message-info';
                infoDiv.textContent = info;
                contentDiv.appendChild(infoDiv);
            }
            
            messageDiv.appendChild(contentDiv);
            chatMessages.appendChild(messageDiv);
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }
        
        // Create loading animation
        function createLoadingAnimation() {
            const loadingDiv = document.createElement('div');
            loadingDiv.className = 'loading';
            for (let i = 0; i < 3; i++) {
                const dot = document.createElement('div');
                loadingDiv.appendChild(dot);
            }
            return loadingDiv;
        }
        
        // Send message
        async function sendMessage() {
            const message = messageInput.value.trim();
            if (!message || !isReady || isWaiting) return;
            
            // Add user message
            addMessage(message, true, `You • ${new Date().toLocaleTimeString()}`);
            messageInput.value = '';
            
            // Show loading
            isWaiting = true;
            updateUI();
            const loadingMsg = createLoadingAnimation();
            addMessage(loadingMsg, false);
            
            try {
                const response = await fetch('/api/chat', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({ message })
                });
                
                const data = await response.json();
                
                // Remove loading message
                chatMessages.removeChild(chatMessages.lastChild);
                
                // Add bot response
                const info = `AI • Confidence: ${data.confidence}% • Category: ${data.category}`;
                addMessage(data.response, false, info);
                
            } catch (error) {
                // Remove loading message
                chatMessages.removeChild(chatMessages.lastChild);
                addMessage('Sorry, I encountered an error. Please try again.', false, 'Error');
                console.error('Chat error:', error);
            }
            
            isWaiting = false;
            updateUI();
        }
        
        // Send example message
        function sendExample(text) {
            messageInput.value = text;
            sendMessage();
        }
        
        // Event listeners
        messageInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                sendMessage();
            }
        });
        
        // Initialize
        checkStatus();
        setInterval(checkStatus, 5000); // Check status every 5 seconds
    </script>
</body>
</html>
```

#### Package.json Setup

```json
{
  "name": "brainjs-chatbot",
  "version": "1.0.0",
  "description": "Full stack chatbot with Brain.js",
  "main": "server.js",
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js"
  },
  "dependencies": {
    "express": "^4.18.2",
    "brain.js": "^2.0.0-beta.2"
  },
  "devDependencies": {
    "nodemon": "^3.0.1"
  }
}
```

#### Database Integration (MongoDB)

```javascript
// database.js - MongoDB integration
const { MongoClient } = require('mongodb');

class ChatDatabase {
  constructor(connectionString) {
    this.client = new MongoClient(connectionString);
    this.db = null;
    this.collection = null;
  }

  async connect() {
    try {
      await this.client.connect();
      this.db = this.client.db('chatbot');
      this.collection = this.db.collection('conversations');
      console.log('✅ Database connected');
    } catch (error) {
      console.error('❌ Database connection failed:', error);
    }
  }

  async saveConversation(userMessage, botResponse, confidence, category) {
    try {
      const conversation = {
        userMessage,
        botResponse,
        confidence: parseFloat(confidence),
        category,
        timestamp: new Date()
      };
      
      await this.collection.insertOne(conversation);
    } catch (error) {
      console.error('Database save error:', error);
    }
  }

  async getRecentConversations(limit = 10) {
    try {
      return await this.collection
        .find()
        .sort({ timestamp: -1 })
        .limit(limit)
        .toArray();
    } catch (error) {
      console.error('Database fetch error:', error);
      return [];
    }
  }

  async getStatistics() {
    try {
      const total = await this.collection.countDocuments();
      const categories = await this.collection.aggregate([
        { $group: { _id: '$category', count: { $sum: 1 } } },
        { $sort: { count: -1 } }
      ]).toArray();

      return { total, categories };
    } catch (error) {
      console.error('Statistics error:', error);
      return { total: 0, categories: [] };
    }
  }
}

module.exports = ChatDatabase;
```

#### Project Setup අනුවන් කරන්න:

```bash
# 1. Project folder එක සාදන්න
mkdir brainjs-chatbot
cd brainjs-chatbot

# 2. Package.json initialize කරන්න
npm init -y

# 3. Dependencies install කරන්න
npm install express brain.js

# 4. Development dependencies (optional)
npm install --save-dev nodemon

# 5. Folders සාදන්න
mkdir public

# 6. Files create කරන්න
# server.js, public/index.html

# 7. Server එක run කරන්න
node server.js

# 8. Browser එකේ visit කරන්න
# http://localhost:3000
```

---

## 7. Tips සහ Best Practices

### 🐛 Brain.js Models Debug කරන විධිය

```javascript
// debugging-techniques.js
const brain = require('brain.js');

class NetworkDebugger {
  constructor() {
    this.network = null;
    this.trainingHistory = [];
    this.debugInfo = {};
  }

  createNetwork(config = {}) {
    this.network = new brain.NeuralNetwork({
      hiddenLayers: [4, 3],
      learningRate: 0.3,
      ...config
    });
    
    this.debugInfo.config = config;
    console.log("🔧 Network created with config:", config);
  }

  trainWithDebugging(data, options = {}) {
    console.log("🔍 Starting debug training...");
    console.log("📊 Training data analysis:");
    
    // Analyze training data
    this.analyzeTrainingData(data);
    
    const defaultOptions = {
      iterations: 1000,
      errorThresh: 0.005,
      log: true,
      logPeriod: 100,
      callback: (stats) => {
        this.trainingHistory.push({
          iteration: stats.iterations,
          error: stats.error,
          timestamp: Date.now()
        });
        
        // Debug callbacks
        if (stats.iterations % 500 === 0) {
          console.log(`🧠 Debug Info at ${stats.iterations}:`);
          console.log(`   Error: ${stats.error.toFixed(6)}`);
          console.log(`   Learning trend: ${this.getLearningTrend()}`);
        }
        
        // Early stopping for debugging
        if (stats.error < 0.001) {
          console.log("🎯 Early stop - very low error achieved!");
          return true;
        }
        
        if (stats.iterations > 50000 && stats.error > 0.1) {
          console.log("⚠️ Early stop - possible learning issue");
          return true;
        }
      }
    };

    const mergedOptions = { ...defaultOptions, ...options };
    
    try {
      const stats = this.network.train(data, mergedOptions);
      
      console.log("📈 Training completed:");
      console.log(`   Final error: ${stats.error}`);
      console.log(`   Iterations: ${stats.iterations}`);
      console.log(`   Training time: ${this.getTrainingTime()}ms`);
      
      this.debugInfo.finalStats = stats;
      return stats;
      
    } catch (error) {
      console.error("❌ Training failed:", error);
      this.debugInfo.error = error.message;
      throw error;
    }
  }

  analyzeTrainingData(data) {
    console.log(`   📦 Data points: ${data.length}`);
    
    if (data.length === 0) {
      console.warn("⚠️ No training data!");
      return;
    }

    // Input analysis
    const inputSizes = data.map(d => d.input.length);
    const outputSizes = data.map(d => d.output.length);
    
    console.log(`   🔢 Input size range: ${Math.min(...inputSizes)} - ${Math.max(...inputSizes)}`);
    console.log(`   🎯 Output size range: ${Math.min(...outputSizes)} - ${Math.max(...outputSizes)}`);
    
    // Data distribution
    const inputRanges = this.getDataRanges(data.map(d => d.input));
    console.log(`   📊 Input value ranges:`, inputRanges);
    
    // Check for duplicates
    const duplicates = this.findDuplicates(data);
    if (duplicates.length > 0) {
      console.warn(`⚠️ Found ${duplicates.length} duplicate data points`);
    }
  }

  getDataRanges(inputs) {
    if (inputs.length === 0) return {};
    
    const flattened = inputs.flat();
    return {
      min: Math.min(...flattened).toFixed(3),
      max: Math.max(...flattened).toFixed(3),
      avg: (flattened.reduce((a, b) => a + b, 0) / flattened.length).toFixed(3)
    };
  }

  findDuplicates(data) {
    const seen = new Set();
    const duplicates = [];
    
    data.forEach((item, index) => {
      const key = JSON.stringify(item);
      if (seen.has(key)) {
        duplicates.push(index);
      } else {
        seen.add(key);
      }
    });
    
    return duplicates;
  }

  getLearningTrend() {
    if (this.trainingHistory.length < 2) return "insufficient data";
    
    const recent = this.trainingHistory.slice(-5);
    const isImproving = recent.every((curr, i) => 
      i === 0 || curr.error <= recent[i-1].error
    );
    
    return isImproving ? "improving ✅" : "stagnating ⚠️";
  }

  getTrainingTime() {
    if (this.trainingHistory.length === 0) return 0;
    
    const start = this.trainingHistory[0].timestamp;
    const end = this.trainingHistory[this.trainingHistory.length - 1].timestamp;
    return end - start;
  }

  testPredictions(testData) {
    console.log("\n🧪 Testing predictions:");
    
    testData.forEach((test, index) => {
      const prediction = this.network.run(test.input);
      const expected = test.expected || test.output;
      
      console.log(`\n📝 Test ${index + 1}:`);
      console.log(`   Input: [${test.input.join(', ')}]`);
      console.log(`   Expected: [${expected.join(', ')}]`);
      console.log(`   Predicted: [${prediction.map(p => p.toFixed(4)).join(', ')}]`);
      
      if (expected) {
        const error = this.calculateError(expected, prediction);
        const accuracy = ((1 - error) * 100).toFixed(1);
        console.log(`   Accuracy: ${accuracy}%`);
      }
    });
  }

  calculateError(expected, predicted) {
    let sum = 0;
    for (let i = 0; i < expected.length; i++) {
      sum += Math.pow(expected[i] - predicted[i], 2);
    }
    return Math.sqrt(sum / expected.length);
  }

  generateDebugReport() {
    console.log("\n📋 Debug Report:");
    console.log("================");
    
    console.log("🏗️ Network Configuration:", this.debugInfo.config);
    console.log("📊 Final Statistics:", this.debugInfo.finalStats);
    console.log("⏱️ Training History Points:", this.trainingHistory.length);
    
    if (this.debugInfo.error) {
      console.log("❌ Errors:", this.debugInfo.error);
    }
    
    // Performance metrics
    if (this.trainingHistory.length > 0) {
      const errorReduction = this.trainingHistory[0].error - this.trainingHistory[this.trainingHistory.length - 1].error;
      console.log(`📈 Error Reduction: ${(errorReduction * 100).toFixed(2)}%`);
    }
  }
}

// Usage Example
console.log("🔬 Brain.js Debugging Demo");

const debugger = new NetworkDebugger();

// Create network
debugger.createNetwork({
  hiddenLayers: [6, 4],
  learningRate: 0.2
});

// Sample data for debugging
const debugData = [
  { input: [0, 0], output: [0] },
  { input: [0, 1], output: [1] },
  { input: [1, 0], output: [1] },
  { input: [1, 1], output: [0] }
];

// Train with debugging
try {
  debugger.trainWithDebugging(debugData, {
    iterations: 5000,
    errorThresh: 0.01
  });
  
  // Test predictions
  debugger.testPredictions([
    { input: [0, 0], expected: [0] },
    { input: [0.5, 0.5], expected: null }, // Unknown expected result
    { input: [1, 1], expected: [0] }
  ]);
  
  // Generate report
  debugger.generateDebugReport();
  
} catch (error) {
  console.error("Debugging failed:", error);
}
```

### ⚡ Performance Optimization Tips

```javascript
// performance-optimization.js
const brain = require('brain.js');

class PerformanceOptimizer {
  static optimizeNetworkStructure(inputSize, outputSize, dataSize) {
    console.log("🔧 Network Structure Optimization");
    
    // Rule of thumb calculations
    const hiddenNeurons = Math.ceil((inputSize + outputSize) * 2/3);
    const layers = dataSize < 100 ? 1 : dataSize < 1000 ? 2 : 3;
    
    console.log(`📊 Recommended structure for ${dataSize} data points:`);
    console.log(`   Input size: ${inputSize}`);
    console.log(`   Hidden layers: ${layers}`);
    console.log(`   Neurons per layer: ${hiddenNeurons}`);
    console.log(`   Output size: ${outputSize}`);
    
    // Generate layer configuration
    const hiddenLayers = [];
    for (let i = 0; i < layers; i++) {
      // Decreasing layer size
      const layerSize = Math.max(3, Math.floor(hiddenNeurons * (0.8 ** i)));
      hiddenLayers.push(layerSize);
    }
    
    return {
      hiddenLayers,
      inputSize,
      outputSize,
      learningRate: this.optimizeLearningRate(dataSize)
    };
  }

  static optimizeLearningRate(dataSize) {
    // Smaller datasets need higher learning rates
    if (dataSize < 50) return 0.8;
    if (dataSize < 200) return 0.5;
    if (dataSize < 1000) return 0.3;
    return 0.1;
  }

  static preprocessData(data) {
    console.log("🔄 Data Preprocessing for Performance");
    
    // Normalize inputs to 0-1 range
    const normalizedData = data.map(item => {
      const normalizedInput = this.normalizeArray(item.input);
      const normalizedOutput = Array.isArray(item.output) 
        ? this.normalizeArray(item.output)
        : item.output;
      
      return {
        input: normalizedInput,
        output: normalizedOutput
      };
    });
    
    console.log("✅ Data normalized for better performance");
    return normalizedData;
  }

  static normalizeArray(arr) {
    const min = Math.min(...arr);
    const max = Math.max(...arr);
    const range = max - min;
    
    if (range === 0) return arr.map(() => 0.5); // Handle constant arrays
    
    return arr.map(val => (val - min) / range);
  }

  static createOptimizedNetwork(inputSize, outputSize, dataSize) {
    const config = this.optimizeNetworkStructure(inputSize, outputSize, dataSize);
    
    return new brain.NeuralNetwork({
      inputSize: config.inputSize,
      hiddenLayers: config.hiddenLayers,
      outputSize: config.outputSize,
      learningRate: config.learningRate,
      momentum: 0.1, // Add momentum for better convergence
      activation: 'sigmoid' // Most stable for general use
    });
  }

  static getOptimalTrainingOptions(dataSize) {
    console.log("⚙️ Optimizing Training Parameters");
    
    const baseIterations = Math.min(20000, dataSize * 100);
    const logPeriod = Math.max(100, Math.floor(baseIterations / 20));
    
    const options = {
      iterations: baseIterations,
      errorThresh: dataSize < 100 ? 0.01 : 0.005,
      log: true,
      logPeriod: logPeriod,
      learningRate: this.optimizeLearningRate(dataSize),
      momentum: 0.1
    };
    
    console.log("📈 Optimal training options:", options);
    return options;
  }

  static benchmarkPerformance(network, testData) {
    console.log("\n⏱️ Performance Benchmark");
    
    const startTime = performance.now();
    const predictions = testData.map(test => network.run(test.input));
    const endTime = performance.now();
    
    const totalTime = endTime - startTime;
    const avgTime = totalTime / testData.length;
    const predictionsPerSecond = 1000 / avgTime;
    
    console.log(`📊 Benchmark Results:`);
    console.log(`   Total time: ${totalTime.toFixed(2)}ms`);
    console.log(`   Average time per prediction: ${avgTime.toFixed(2)}ms`);
    console.log(`   Predictions per second: ${predictionsPerSecond.toFixed(0)}`);
    
    return {
      totalTime,
      avgTime,
      predictionsPerSecond
    };
  }
}

// Performance Demo
console.log("⚡ Brain.js Performance Optimization Demo");

// Sample data
const sampleData = [
  { input: [0.1, 0.2, 0.3], output: [0.8] },
  { input: [0.4, 0.5, 0.6], output: [0.2] },
  { input: [0.7, 0.8, 0.9], output: [0.1] },
  { input: [0.2, 0.4, 0.6], output: [0.7] },
  { input: [0.3, 0.6, 0.9], output: [0.3] }
];

// Optimize and create network
const optimizedNetwork = PerformanceOptimizer.createOptimizedNetwork(3, 1, sampleData.length);

// Preprocess data
const processedData = PerformanceOptimizer.preprocessData(sampleData);

// Get optimal training options
const trainingOptions = PerformanceOptimizer.getOptimalTrainingOptions(sampleData.length);

// Train network
console.log("\n🏋️ Training Optimized Network...");
const stats = optimizedNetwork.train(processedData, trainingOptions);

console.log("✅ Training completed with optimized settings");
console.log(`Final error: ${stats.error.toFixed(6)}`);

// Benchmark performance
const testData = [
  { input: [0.1, 0.2, 0.3] },
  { input: [0.5, 0.6, 0.7] },
  { input: [0.8, 0.9, 0.1] }
];

PerformanceOptimizer.benchmarkPerformance(optimizedNetwork, testData);
```

### 🆚 Brain.js vs TensorFlow.js - කුමන්ද වඩා හොඳ?

```javascript
// comparison-guide.js

console.log(`
🎯 Brain.js vs TensorFlow.js Comparison Guide
============================================

📊 තුලනාත්මක විශ්ලේෂණය:

┌─────────────────┬──────────────┬───────────────┐
│ Feature         │ Brain.js     │ TensorFlow.js │
├─────────────────┼──────────────┼───────────────┤
│ Learning Curve  │ ⭐⭐⭐⭐⭐      │ ⭐⭐           │
│ Performance     │ ⭐⭐⭐         │ ⭐⭐⭐⭐⭐       │
│ Features        │ ⭐⭐⭐         │ ⭐⭐⭐⭐⭐       │
│ Community       │ ⭐⭐⭐         │ ⭐⭐⭐⭐⭐       │
│ Documentation   │ ⭐⭐⭐⭐        │ ⭐⭐⭐⭐⭐       │
│ Bundle Size     │ ⭐⭐⭐⭐⭐      │ ⭐⭐           │
│ Browser Support │ ⭐⭐⭐⭐⭐      │ ⭐⭐⭐⭐        │
└─────────────────┴──────────────┴───────────────┘

🤔 කවදා Brain.js use කරන්නද?
✅ Small to medium projects
✅ Rapid prototyping
✅ Learning neural networks
✅ Simple chatbots
✅ Basic prediction models
✅ Educational purposes
✅ Quick demos

🤔 කවදා TensorFlow.js use කරන්නද?
✅ Production applications
✅ Complex deep learning
✅ Computer vision
✅ Large datasets
✅ Advanced AI features
✅ Research projects
✅ Enterprise solutions

📝 Code Comparison:
==================

Brain.js - Simple XOR:
----------------------
const brain = require('brain.js');
const network = new brain.NeuralNetwork();
network.train([
  { input: [0, 0], output: [0] },
  { input: [1, 1], output: [0] }
]);
console.log(network.run([1, 0])); // ~0.9

TensorFlow.js - Same XOR:
-------------------------
const tf = require('@tensorflow/tfjs');
const model = tf.sequential({
  layers: [
    tf.layers.dense({ units: 3, inputShape: [2], activation: 'sigmoid' }),
    tf.layers.dense({ units: 1, activation: 'sigmoid' })
  ]
});
model.compile({ optimizer: 'adam', loss: 'meanSquaredError' });
// ... more complex setup required

🎯 Recommendation for Sri Lankan Developers:
==========================================

🔰 Beginners → Start with Brain.js
   - Easy to understand
   - Quick results
   - Good for learning concepts
   - Sinhala tutorials available

🚀 Intermediate → Brain.js for prototypes, TensorFlow.js for production
   - Use Brain.js for proof of concepts
   - Migrate to TensorFlow.js for scaling
   - Learn both gradually

💼 Advanced → Choose based on requirements
   - Small projects → Brain.js
   - Complex AI → TensorFlow.js
   - Hybrid approach for different components

📚 Learning Path Suggestion:
===========================
1. Master Brain.js basics (1-2 months)
2. Build 3-5 projects with Brain.js
3. Learn TensorFlow.js concepts
4. Compare performance for your use cases
5. Choose the right tool for each project
`);

// Practical comparison function
function compareLibraries() {
  console.log("\n🔬 Practical Comparison Demo:");
  
  // Brain.js implementation
  console.log("\n📦 Brain.js Implementation:");
  const brainStart = Date.now();
  
  const brain = require('brain.js');
  const network = new brain.NeuralNetwork();
  
  const data = [
    { input: [0, 0], output: [0] },
    { input: [0, 1], output: [1] },
    { input: [1, 0], output: [1] },
    { input: [1, 1], output: [0] }
  ];
  
  network.train(data, { iterations: 1000, log: false });
  const brainResult = network.run([1, 0]);
  const brainEnd = Date.now();
  
  console.log(`Result: ${brainResult[0].toFixed(4)}`);
  console.log(`Time: ${brainEnd - brainStart}ms`);
  console.log(`Code lines: ~10`);
  
  // Note: TensorFlow.js comparison would require actual TF.js installation
  console.log("\n📦 TensorFlow.js would require:");
  console.log("• More setup code (~30+ lines)");
  console.log("• Complex model compilation");
  console.log("• Tensor management");
  console.log("• But potentially better performance for large datasets");
}

compareLibraries();
```

### 🎯 Best Practices Summary

```markdown
## 🏆 Brain.js Best Practices - සිංහල

### 1. 📊 Data Preparation
- **Normalize data** 0-1 range එකට
- **Clean duplicates** duplicate data points remove කරන්න
- **Balanced datasets** use කරන්න
- **Sufficient data** අවම වශයෙන් 50+ samples

### 2. 🏗️ Network Architecture
- **Start simple** 1-2 hidden layers වලින් ආරම්භ කරන්න
- **Gradual complexity** අවශ්‍ය නම් layers add කරන්න  
- **Rule of thumb**: hidden neurons = (input + output) * 2/3
- **Avoid overfitting** layers වැඩියෙන් add නොකරන්න

### 3. ⚙️ Training Parameters
- **Learning rate**: 0.1-0.3 (small data), 0.01-0.1 (large data)
- **Iterations**: Data size × 100 (minimum)
- **Error threshold**: 0.01 (small data), 0.005 (large data)
- **Momentum**: 0.1 stability සඳහා

### 4. 🔧 Performance Tips
- **Preprocess data** training කිරීමට කලින්
- **Batch training** large datasets සඳහා
- **Early stopping** implement කරන්න
- **Save models** re-training avoid කරන්න

### 5. 🐛 Debugging
- **Monitor error trends** training අතරතුර
- **Test incrementally** small changes test කරන්න
- **Validate results** known data වලින්
- **Log everything** debugging සඳහා

### 6. 📱 Production Ready
- **Error handling** add කරන්න
- **Input validation** implement කරන්න
- **Model versioning** maintain කරන්න
- **Performance monitoring** production එකේ

### 7. 🔄 Maintenance
- **Regular retraining** new data සමග
- **Model updates** gradual improvements
- **Backup models** previous versions save කරන්න
- **Documentation** maintain කරන්න
```

---

## 🎓 මුළු Course එක Complete කළ පසු...

**ඔබ දැන් Brain.js expert කෙනෙක්!** 🎉

### 📚 ඊළඟට ඉගෙන ගන්න:
1. **TensorFlow.js** - Advanced AI projects සඳහා
2. **Node.js Advanced** - Better backend development
3. **React/Vue.js** - Modern frontend frameworks
4. **Database Management** - MongoDB, PostgreSQL
5. **Cloud Deployment** - AWS, Google Cloud

### 🚀 Project Ideas:
1. **E-commerce Recommendation System**
2. **Stock Price Prediction**  
3. **Image Recognition (with TensorFlow.js)**
4. **Natural Language Processing**
5. **Game AI Development**

### 🌟 Advanced Resources:
- [Brain.js Documentation](https://brain.js.org/)
- [Neural Networks Theory](https://neuralnetworksanddeeplearning.com/)
- [JavaScript ML Community](https://js.tensorflow.org/)

---

**සුභ පැතුම්! ඔබේ AI journey එක සාර්ථක වේවා! 🧠✨**

---

*මෙම tutorial එක ඔබට ප්‍රයෝජනවත් වුනා නම්, share කරන්න සහ වෙනත් developers ලාට help කරන්න!* 💝
