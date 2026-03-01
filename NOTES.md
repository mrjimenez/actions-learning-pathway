# Node.js and Package Management: Key Concepts

1. Understanding npx (Node Package Execute)
   Definition: A tool bundled with npm that executes packages without needing to install them globally.
   Main Uses:
   Running "one-off" commands (like create-react-app).
   Ensuring you are always using the latest version of a tool.
   Executing local binaries stored in node_modules/.bin easily.

2. npx inside package.json Scripts
   Redundancy: Using npx inside the "scripts" section of a package.json is usually unnecessary.
   Automatic Path inclusion: When you run npm run `<script>`, npm automatically includes the local node_modules in the execution path.
   Best Practice: Use direct commands (e.g., "test": "eslint ." instead of "test": "npx eslint .").

3. Versioning Strategy for New Projects
   Initial Version: Start with 0.1.0 for unstable/development phases or 1.0.0 for your first stable release.
   Dependency Symbols:
   ^ (Caret): Allows Minor and Patch updates (Standard).
   ~ (Tilde): Allows only Patch updates (Security fixes).
   No symbol: Locks the version exactly.

4. Finding and Updating Packages
   Check Latest Version: Use npm view `<package-name>` version.
   Check for Outdated Packages: Use npm outdated to see a table of current vs. latest versions.
   Force Update Everything:
   Run npx npm-check-updates -u to update package.json.
   Run npm install to sync node_modules and the lockfile.
   Caution: Major version jumps (e.g., v1 to v2) can contain "breaking changes" that require code adjustments.
