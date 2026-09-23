# Changelog

## 1.0.0
- Recompiled all gameplay into modular systems
- Added achievements, quest chain, daily quests, and streaks
- Added optional cloud saves, leaderboard, and guilds
- Added responsive desktop/mobile interface and Tauri scaffold

## 1.1.0
- Added cooperative guild goals for Energy and Research Data
- Added atomic guild contribution RPC and contribution ledger
- Added per-player guild contribution rankings
- Added goal progress, completion states, and reward metadata

## 1.2.0
- Added server-authoritative Energy and Research Data wallets
- Added server-side time accrual based on server-owned machine counts
- Added server-validated clicks, machine purchases, conversions, and guild contributions
- Removed direct client write access to authoritative economy tables
- Added versioned economy snapshots and database transactions

## 1.3.0 Social Update
- Added friend requests, acceptance, rejection, and removal
- Added friend list with presence and VIP badges
- Added server-authoritative daily friend gifts
- Added read-only friend foundry visits
- Added VIP levels 1-5, supporter titles, frames, and gift allowances
- Kept VIP assignment server/admin controlled

## 1.4.0 Guild Research
- Added Production, Offline Systems, and Social Network research branches
- Added prerequisites, levels, escalating costs, and maximum levels
- Added server-authoritative guild research contributions
- Applied Production research to server-authoritative energy accrual
- Added guild-wide tree UI and live multiplier summary

## 1.5.0 Seasonal Events
- Added active season schedule, server-verified challenges, Void Shards, XP, and levels
- Added free cosmetic reward track and server-side reward claiming
- Added seasonal leaderboard
- Split seasonal database service, interface renderer, and controller into separate modules

## 1.6.0 World Events
- Added global cooperative events with server-authoritative contributions
- Added global milestones and contributor rewards
- Added top-contributor rankings and personal contribution tracking
- Added Planetary Reactor launch event
- Split event service, renderer, and controller into separate modules

### 1.7.0 Offline Progress and Automation
- Added detailed while-away earnings summaries and configurable offline caps
- Added server-authoritative offline accrual logs using trusted database time
- Activated guild Offline Cells efficiency and Deep Storage cap bonuses
- Added local and server-backed machine automators with per-machine controls
- Added responsive Automation tab and automatic verified purchases

### 1.8.0 Autonomous Foundry
- Added target-based machine purchasing rules
- Added ordered, cheapest, best-value, balanced, and highest-tier strategies
- Added protected Energy reserves and per-cycle action limits
- Added automated Research Data conversion thresholds and percentages
- Added server-authoritative rule storage, execution, and activity history
- Rebuilt the Automation tab as a responsive Control Center

### 1.8.1 Launch Readiness
- Added versioned local and cloud-save envelopes
- Removed authoritative economy fields from cloud-save uploads
- Added password reset and confirmation resend actions
- Added account deletion through a server-owned RPC
- Added launch diagnostics for authentication, economy, saves, and automation
- Added development and production build-channel flags

### 1.8.1 Guild Hotfix
- Replaced schema-dependent `gen_random_bytes` invite-code generation with PostgreSQL UUID-based generation
- Added invite-code collision checking to guild creation

### 1.8.2 VIP Leaderboards
- Added VIP tier badges to the global leaderboard
- Added a personal global-rank card for every signed-in player
- Increased the visible leaderboard to the top 100 players
- Highlighted the signed-in player in the ranking list

### 1.8.3 VIP Pricing
- Added permanent one-time pricing to purchasable VIP tiers
- Set Supporter to $5, Bronze to $10, Silver to $20, and Gold to $40 USD
- Marked Founder as permanently unavailable for purchase
- Reserved Founder status for verified development testers
- Added disabled purchase placeholders until trusted payment fulfillment is connected

### 1.9.0 Modern Interface
- Rebuilt the visual system with a modern glass-and-neon design
- Added sticky responsive header and navigation
- Added icon-enhanced page navigation and animated page transitions
- Redesigned panels, machine cards, quests, leaderboards, VIP tiers, forms, and event pages
- Improved mobile layouts, focus states, contrast, and reduced-motion support

### 2.0.0 Progression Rebalance
- Rebuilt achievements as difficult milestones with machine-specific boosts
- Reworked research into smaller machine-specific production upgrades
- Added server-authoritative research purchases
- Added functional local and online Ascension at 10 million run Energy
- Added permanent Quantum Cores with +12% machine output per core
- Added server-authoritative achievement, research, core, and Ascension state

### 2.0.1 Interface Recovery Hotfix
- Restored reliable navigation with an independent click fallback
- Fixed save migration for machines, research, achievements, daily data, and automation
- Prevented stale daily-quest IDs from stopping page rendering
- Added visible startup error reporting instead of silent empty pages

### 2.1.0 Navigation and Account Layout
- Moved Account into the persistent top header
- Merged Stats and save management into the Account drawer
- Removed Account and Stats from page navigation
- Reworked the selector into a non-scrolling responsive grid
- Moved VIP to the final navigation position

### 2.1.1 Online Feature Sign-In Gates
- Required an authenticated account for Daily, Leaderboard, Guild, Friends, Season, and World Event pages
- Added dedicated sign-in and account-creation prompts to protected pages
- Prevented protected refresh and action handlers from running while signed out
- Connected protected-page prompts directly to the persistent Account panel

### 2.1.2 Mobile Account Panel
- Converted the Account drawer into a full-screen mobile sheet
- Added Account and Stats tabs inside the mobile panel
- Added safe-area spacing and momentum scrolling
- Stacked all account, recovery, deletion, and save controls for touch screens
- Prevented input zoom by using mobile-safe field sizing

### 2.2.0 Tester Preview
- Added authenticated tester feedback inside the Account panel
- Added bug, balance, interface, suggestion, and general feedback categories
- Added a five-point experience rating and optional follow-up consent
- Attached app version, build channel, and limited device information to reports
- Switched the distributed package to the testing channel and hid development diagnostics

### 2.2.0 Windows Tester Installer
- Configured the Windows bundle for a current-user NSIS setup executable
- Added one-step PowerShell and batch build helpers
- Added automatic copying to Neon-Foundry-Tester-Setup.exe

### 2.2.1 Windows Builder Repair
- Removed the fixed bundle-folder assumption from the Windows build helper
- Added recursive installer discovery for default, target-triple, and custom Cargo output paths
- Added windows-build.log and explicit npm/Tauri exit-code checks
- Added clearer extraction and failure instructions

### 2.2.2 Tauri Dependency Synchronization
- Pinned the Tauri CLI and JavaScript API to the 2.11 minor release line
- Pinned the Rust Tauri runtime to the matching 2.11 minor release line
- Added automatic cleanup of stale npm and Cargo lock files before Windows builds
- Added Tauri environment information to windows-build.log

### 2.2.3 PowerShell Native Command Repair
- Prevented informational npm and Tauri stderr output from terminating the builder
- Converted native command output to ordinary log strings before processing
- Uses native process exit codes rather than PowerShell NativeCommandError wrappers

### 2.2.4 Windows Exit-Code Repair
- Prevented native command log lines from being returned as part of the exit-code value
- Ensured npm and Tauri helper calls return exactly one integer exit code
- Preserved live console output and windows-build.log capture

### 2.2.5 Windows Icon Repair
- Added the required Windows icon.ico resource
- Added a high-resolution PNG application icon
- Connected both icon resources to the Tauri bundle configuration

### 2.3.0 Beta Launch Analytics
- Added a required pre-release beta acknowledgement prompt
- Added the official Discord invite to the launch prompt
- Added authenticated launch, acknowledgement, and Discord-open tracking
- Added a database-enforced administrator launch-statistics view
- Added version, build-channel, tester activity, and feedback breakdowns
