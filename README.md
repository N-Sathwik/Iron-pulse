# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) (or [oxc](https://oxc.rs) when used in [rolldown-vite](https://vite.dev/guide/rolldown)) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

IronPulse - Modern Gym Management System 🏋️‍♂️IronPulse is a next-generation SaaS application designed for gym owners and fitness centers. It streamlines daily operations with real-time analytics, member management, and AI-driven workout planning—all wrapped in a sleek, responsive interface with Dark Mode support.🚀 Live Demo[Insert your Vercel/Netlify Link Here]✨ Key Features📊 Interactive DashboardReal-time metrics for Active Members, Churn Rate, and Revenue.Visual data analytics using interactive charts (Recharts).Quick access widgets for Recent Signups and Daily Check-Ins.🔐 Smart Access ControlOTP-Based Check-In System: Secure, dynamic 6-digit codes for facility access.Kiosk Mode: Dedicated interface for gym entry points.QR Code Ready: UI placeholders for future QR integration.🤖 AI Workout GeneratorSmart Plans: Generates personalized workout routines (Strength, HIIT, Cardio) in seconds.Detailed Breakdowns: Automatic creation of sets, reps, and rest intervals.Session Tracking: Interactive "Start Session" mode for members to track live progress.⚙️ Advanced CustomizationGlobal Dark Mode: Fully responsive dark theme powered by Tailwind CSS.Settings Hub: Manage notifications, profile details, security (2FA), and billing invoices.Responsive Sidebar: Mobile-first navigation with hamburger menu support.🛠️ Tech StackFrontend Framework: React 18 (Vite)Language: TypeScriptStyling: Tailwind CSSState Management: Zustand (Global Store)Icons: Lucide ReactCharts: RechartsRouting: React Router v6📸 ScreenshotsDashboard (Light)Dark Mode Support[Place Screenshot Here][Place Screenshot Here]AI Workout GeneratorOTP Check-In Kiosk[Place Screenshot Here][Place Screenshot Here]💻 Getting StartedFollow these steps to run IronPulse locally on your machine.PrerequisitesNode.js (v16 or higher)npm or yarnInstallationClone the repositoryBashgit clone https://github.com/N-Sathwik/iron-pulse.git
cd iron-pulse
Install dependenciesBashnpm install
Start the development serverBashnpm run dev
Open your browserNavigate to http://localhost:5173 to view the app.📂 Project StructureBashsrc/
├── components/     # Reusable UI (Cards, Modals)
├── features/       # Page Logic (Dashboard, Auth, Members, Check-In)
├── layouts/        # Sidebar & Layout Wrappers
├── stores/         # Zustand Global State (Auth, Workout, Theme)
└── App.tsx         # Main Router Configuration
🔮 Future Roadmap[ ] Backend Integration: Connect to Supabase/Firebase for real database persistence.[ ] Member Portal: Dedicated login for gym members to view their own progress.[ ] Payment Gateway: Stripe integration for subscription billing.👨‍💻 AuthorSathwik the DeveloperFull Stack Developer & UI/UX Enthusiast.Building scalable web applications with modern tech stacks.Built with ❤️ for the fitness community.
