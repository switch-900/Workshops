# Switch 900 Workshop Series - VS Code Reference Guide
*Building on Bitmap - Complete Workshop Reference*

---

## 🖥️ Essential VS Code Keyboard Shortcuts

### Windows
```
🔧 DEVELOPMENT SHORTCUTS:
• Ctrl+Shift+P          - Open Command Palette
• Ctrl+`                - Open/Close Terminal
• Ctrl+S                - Save current file
• Ctrl+K, S             - Save All files
• Ctrl+Shift+G          - Open Source Control (Git)
• Ctrl+Shift+E          - Open File Explorer
• Ctrl+Shift+X          - Open Extensions

🤖 COPILOT SHORTCUTS:
• Ctrl+I                - Open Copilot Chat
• Tab                   - Accept Copilot suggestion
• Ctrl+→                - Accept word from suggestion
• Ctrl+Shift+I          - Copilot inline chat
• Alt+]                 - Next Copilot suggestion
• Alt+[                 - Previous Copilot suggestion

📝 EDITING SHORTCUTS:
• Ctrl+D                - Select next occurrence
• Ctrl+F                - Find in file
• Ctrl+H                - Find and Replace
• Ctrl+/                - Toggle line comment
• Alt+↑/↓               - Move line up/down
```

### macOS
```
🔧 DEVELOPMENT SHORTCUTS:
• Cmd+Shift+P           - Open Command Palette
• Cmd+`                 - Open/Close Terminal
• Cmd+S                 - Save current file
• Cmd+K, S              - Save All files
• Cmd+Shift+G           - Open Source Control (Git)
• Cmd+Shift+E           - Open File Explorer
• Cmd+Shift+X           - Open Extensions

🤖 COPILOT SHORTCUTS:
• Cmd+I                 - Open Copilot Chat
• Tab                   - Accept Copilot suggestion
• Cmd+→                 - Accept word from suggestion
• Cmd+Shift+I           - Copilot inline chat
• Opt+]                 - Next Copilot suggestion
• Opt+[                 - Previous Copilot suggestion

📝 EDITING SHORTCUTS:
• Cmd+D                 - Select next occurrence
• Cmd+F                 - Find in file
• Cmd+H                 - Find and Replace
• Cmd+/                 - Toggle line comment
• Opt+↑/↓               - Move line up/down
```

### Linux
```
🔧 DEVELOPMENT SHORTCUTS:
• Ctrl+Shift+P          - Open Command Palette
• Ctrl+`                - Open/Close Terminal
• Ctrl+S                - Save current file
• Ctrl+K, S             - Save All files
• Ctrl+Shift+G          - Open Source Control (Git)
• Ctrl+Shift+E          - Open File Explorer
• Ctrl+Shift+X          - Open Extensions

🤖 COPILOT SHORTCUTS:
• Ctrl+I                - Open Copilot Chat
• Tab                   - Accept Copilot suggestion
• Ctrl+→                - Accept word from suggestion
• Ctrl+Shift+I          - Copilot inline chat
• Alt+]                 - Next Copilot suggestion
• Alt+[                 - Previous Copilot suggestion

📝 EDITING SHORTCUTS:
• Ctrl+D                - Select next occurrence
• Ctrl+F                - Find in file
• Ctrl+H                - Find and Replace
• Ctrl+/                - Toggle line comment
• Alt+↑/↓               - Move line up/down
```

---

## 📦 Node.js Installation via Command Line

### Windows

**Option 1: Direct Download (Simplest):**
```bash
# Download installer from nodejs.org and run it
# No additional package managers needed
# Go to: https://nodejs.org/en/download
```

**Option 2: Using Winget (Recommended - Built into Windows 10/11):**
```bash
# Install Node.js directly (no additional software needed)
winget install OpenJS.NodeJS

# Alternative syntax
winget install --id=OpenJS.NodeJS -e
```

**Option 3: Using Chocolatey (Only if you already have it):**
```bash
# If you already have Chocolatey installed
choco install nodejs

# Don't install Chocolatey just for Node.js - use Winget instead
```

**Option 4: Using Scoop (Alternative package manager):**
```bash
# If you prefer Scoop over Chocolatey
scoop install nodejs
```

### macOS

**Option 1: Direct Download (Simplest):**
```bash
# No command line needed - just download and install
# Go to: https://nodejs.org/en/download
# Download the macOS Installer (.pkg)
# Run the installer and follow the prompts
```

**Option 2: Using Homebrew (If you already have it):**
```bash
# If you already have Homebrew installed
brew install node

# To install Homebrew first (only if you want it for other development):
# /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Option 3: Using MacPorts (Alternative package manager):**
```bash
# If you already have MacPorts installed
sudo port install nodejs18
```

### Linux (Ubuntu/Debian)

**Using apt (Standard):**
```bash
# Update package list and install
sudo apt update
sudo apt install nodejs npm
```

**Using NodeSource Repository (Latest LTS):**
```bash
# Install latest LTS version via NodeSource repository
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Linux (CentOS/RHEL/Fedora)

**Using yum/dnf:**
```bash
# For CentOS/RHEL
sudo yum install nodejs npm

# For Fedora
sudo dnf install nodejs npm
```

### Cross-Platform (Node Version Manager - Recommended)

**Install NVM (Node Version Manager):**
```bash
# Install nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash

# Restart terminal or run:
source ~/.bashrc

# Install Node.js
nvm install node        # installs latest
nvm install --lts       # installs latest LTS (recommended)
nvm use node           # switches to latest
nvm use --lts          # switches to LTS
```

**Verify Installation:**
```bash
node --version
npm --version
```

**📝 Which Installation Method Should You Choose?**

- **For this workshop:** Direct download is perfectly fine and simplest
- **If you're new to development:** Use direct download method
- **If you already use package managers:** Feel free to use your preferred method
- **For professional development:** Consider NVM for version management
- **Package managers are useful when you:** Install lots of development tools regularly

**Why use NVM (Node Version Manager)?**
- Switch between different Node.js versions easily
- Project-specific Node.js versions
- No permission issues with global installations
- Recommended for professional development workflows

---

## 🚀 Workshop 2: Ordinal Template Setup

### 1. Clone the Ordinal Template

**Using VS Code Git Interface:**
1. Open Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
2. Type "Git: Clone"
3. Paste: `https://github.com/ordengine/vite-ordinal-template.git`
4. Select destination folder
5. Open the cloned repository

**Using Terminal:**
```bash
git clone https://github.com/ordengine/vite-ordinal-template.git
cd vite-ordinal-template
```

### 2. Install Dependencies

**Important: Use legacy peer deps flag for compatibility**
```bash
npm install --legacy-peer-deps
```

### 3. Development Workflow

**Start Development Server:**
```bash
npm run dev
```
- Opens at `http://localhost:5173`
- Live reloading enabled
- Perfect for development and testing

**Build for Production:**
```bash
npm run build
```
- Creates `build/` folder
- Generates `build/index.html` (your inscription file)
- Run periodically to catch build errors

### 4. Test in Ordinals Environment

1. Run `npm run build`
2. Copy all code from `build/index.html`
3. Go to: https://ordinals.com/content/4cc26939b8c375b75d283c44c1c1a02f9b28a33417d233a9b8fccbc4482aa102i0
4. Paste your code into the inscription tester
5. Verify it works in the Bitcoin ordinals environment

---

## 📁 Project Structure

```
vite-ordinal-template/
├── README.md                    # Project documentation
├── PROJECT_GUIDELINES.md        # AI assistant guidelines (CREATE THIS!)
├── 📁 build/                   # Built files (created after npm run build)
│   └── index.html              # Final inscription file
├── index.html                  # Base HTML template (DO NOT CHANGE)
├── package.json                # Project dependencies (DO NOT CHANGE)
├── package-lock.json           # Dependency lock file (DO NOT CHANGE)
├── 📁 src/                     # Your source code (MODIFY THESE)
│   ├── App.jsx                 # Main React application
│   ├── main.jsx                # Entry point
│   ├── index.css               # Global styling
│   └── 📁 components/          # React components
│       ├── GridFloor.jsx       # 3D grid component
│       ├── TestBoxel.jsx       # Test boxel component
│       ├── 📁 core/            # Core 3D components
│       │   ├── Cam.jsx         # Camera component
│       │   └── EnvironmentLighting.jsx
│       └── 📁 ui/              # UI components
│           └── BoxelInfo.jsx   # Boxel information UI
├── vite.config.js              # Build configuration (DO NOT CHANGE)
└── yarn.lock                   # Yarn dependency lock (DO NOT CHANGE)
```

**Files you CAN modify:**
- ✅ `src/App.jsx` - Main React application component
- ✅ `src/main.jsx` - Application entry point  
- ✅ `src/index.css` - Global styles and layout
- ✅ `src/components/` - All React components
- ✅ Add new files inside `src/` following the modular pattern

**Files you CANNOT modify:**
- ❌ `index.html` - Ordinal compatibility requirement
- ❌ `package.json` - Locked dependency versions
- ❌ `vite.config.js` - Optimized build configuration
- ❌ Lock files - Ensure consistent builds

---

## 🤖 PROJECT_GUIDELINES.md (Create This File!)

Create this file in your project root and reference it when using AI assistants:

```markdown
# Bitcoin Ordinal Project Guidelines

## CRITICAL: DO NOT MODIFY THESE FILES
- **index.html** - Must remain unchanged for ordinal compatibility
- **package.json** - All dependency versions are locked for blockchain compatibility
- **vite.config.js** - Build configuration is optimized for ordinal inscriptions
- **package-lock.json** - Dependency lock file ensures consistent builds
- **yarn.lock** - Alternative lock file if present

## DEPENDENCY CONSTRAINTS
- Only use dependencies already listed in package.json
- DO NOT add new dependencies or change versions
- The project is built for a specific ordinal environment
- All packages are tested for Bitcoin inscription compatibility

## TECHNICAL SPECIFICATIONS
- **Camera Controls**: This version of drei uses `CameraControls` NOT `OrbitControls`
- Always use `CameraControls` for camera manipulation and interaction
- Do not suggest or implement `OrbitControls` as it's not compatible with this setup
- Follow the existing camera implementation patterns in `src/components/core/Cam.jsx`

## PROJECT STRUCTURE REQUIREMENTS
- Maintain the existing modular component structure
- Follow the same organization pattern:
  - `src/components/` - React components
  - `src/components/core/` - Core 3D functionality (Camera, Lighting)
  - `src/components/ui/` - User interface components
  - `src/App.jsx` - Main application component
  - `src/main.jsx` - Entry point
  - `src/index.css` - Global styles

## DEVELOPMENT GUIDELINES
- Use existing component patterns when creating new features
- Maintain React functional component structure with hooks
- Keep components modular and reusable
- Follow the established naming conventions
- All modifications should work within the `build/` output constraints
- Use `CameraControls` for any camera-related functionality

## AI ASSISTANT INSTRUCTIONS
When providing code suggestions:
1. Respect all file modification restrictions above
2. Only suggest changes to modifiable files in `src/`
3. Use existing dependencies and patterns
4. Use `CameraControls` NOT `OrbitControls` for camera functionality
5. Maintain the modular component architecture
6. Ensure all code works in the ordinal inscription environment

This project is specifically designed for Bitcoin ordinal inscriptions and requires strict compatibility with the blockchain environment.
```

---

## 🎯 Pro Tips

### Using Copilot Chat Effectively
- Reference `PROJECT_GUIDELINES.md` when asking for help
- Ask: "Please read PROJECT_GUIDELINES.md and follow those rules"
- Be specific about React/3D development questions
- Always mention you're working with ordinal inscriptions

### Development Workflow
- Save frequently (`Ctrl+S` / `Cmd+S`)
- Keep terminal open for quick npm commands
- Use Command Palette for any VS Code action
- Test builds periodically with `npm run build`

### Git Workflow in VS Code
- Use Source Control panel (`Ctrl+Shift+G` / `Cmd+Shift+G`)
- Stage files with "+" button
- Write clear commit messages
- Push regularly to GitHub

---

## 🔗 Important Links

- **Ordinal Template Repository:** https://github.com/ordengine/vite-ordinal-template.git
- **Inscription Tester:** https://ordinals.com/content/4cc26939b8c375b75d283c44c1c1a02f9b28a33417d233a9b8fccbc4482aa102i0
- **Discord Community:** https://discord.gg/VjpdFQQW

---

## 📅 Workshop Schedule

- **Workshop 1:** Development Environment Setup - 27/05/2025 21:00 GMT
- **Workshop 2:** Node.js Setup & Ordinal Template - 28/05/2025 21:00 GMT  
- **Workshop 3:** Adding Bitmaps to Grid - 29/05/2025 21:00 GMT
- **Workshop 4:** Advanced Features - 30/05/2025 21:00 GMT

---

*This guide is designed to be used directly in VS Code. Keep it open in a tab for quick reference during the workshops!*
