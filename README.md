# CODEROT — GitHub Repository Code Rot Surveyor 🔎🥀

CODEROT is a high-fidelity, client-side React application that diagnoses "code rot" (file staleness + dead functions) in public or private GitHub repositories. It computes precise metrics using the real GitHub REST API directly from the browser, with a stunning, premium aesthetic inspired by **iOS 18 Liquid Glass**.

## 🌟 Key Features
- **Real-time Metric Collection**: Calls the public GitHub REST API directly to extract file sizes, trees, recursive structure, and the exact last commit date for individual files.
- **Durable Rot Score & Grade Calculation**: Determines structural status and assigns solid academic grading ranges from `A` through `F` depending on precise code age distributions.
- **Zombie / Dead Function Analysis**: Fetches raw code contents of top files, scans via regex pattern recognition for function signatures, and tracks references recursively across the rest of scanned modules.
- **Stunning iOS 18 Glassmorphism UI**: Employs deep cosmic space gradients, orbital animations, and backdrop-saturated borders styled completely with custom Tailwind utilities.
- **Autonomous Setup**: Standard SPA design with zero backend servers or secret requirements, ready for high-performance static hosting.
- **Live Local Clock**: Displays localized timezone parameters in a beautiful glass status widget updating with precise second-level precision.
- **Easy Deployment**: Auto-installs Github Pages deployment workflows right out of the box.

---

## 🚀 Quick Start / Local Development

1. **Clone & Setup**:
   ```bash
   git clone <your-repository-url>
   cd coderot
   npm install
   ```

2. **Run Dev Server**:
   ```bash
   npm run dev
   ```
   Open `http://localhost:3000` to start analyzing.

3. **Build Static Bundle**:
   Verify everything transpiles cleanly to modular, fast-loading static assets inside `/dist`:
   ```bash
   npm run build
   ```

---

## 📦 Deploying to GitHub Pages 🌐

This project includes an automated GitHub Actions deployment script. To deploy:

1. Push your code to the `main` branch of your GitHub repository.
2. The Action in `.github/workflows/deploy.yml` will trigger automatically, build your files, and deploy to the pages branch.
3. Make sure to update the `base` property inside `vite.config.ts` if your GitHub repository name is different than `/coderot/`.

---

## 🔒 Configuration & Rate Limits
- Unauthenticated GitHub API calls are limited by GitHub to **60 requests per hour**.
- To prevent going over this limit, the application limits deep scanning to a maximum of **20 files** and raw code content analysis to the top **5 largest files**.
- To remove these limitations and scan deep files or private repositories, paste a **GitHub Personal Access Token (PAT)** in the inline Settings bar in the application header. Your token is stored securely, kept strictly client-side in-memory, and is never logged or dispatched elsewhere.
