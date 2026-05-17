================================================================================
                       TEAM & LEAGUE MANAGEMENT SYSTEM
================================================================================

DESCRIPTION
-----------
A comprehensive Flask-based web application designed to manage match days. 
The system handles player registration, automated team generation for 
10 or 12-player games, and maintains a real-time league leaderboard.

CORE MODULES & WORKFLOW
-----------------------
1. GROUP     : View league members and manage permissions. Admins can 
               promote/demote users between 'Admin' and 'Read-only' roles.
2. PLAYERS   : Maintain the master list of players and ranks for the 
               active league. Create new games and generate invite codes.
3. TEAMS     : Select available players for a specific date, generate 
               balanced "Orange" and "Yellow" teams, and lock rosters.
4. STANDINGS : The Unified Dashboard. Load locked teams, input match 
               points, and view updated league rankings (MP, Pts, Rank).

TECHNICAL STACK
---------------
- Backend    : Python / Flask
- Database   : PostgreSQL (using psycopg2 and RealDictCursor)
- Frontend   : Jinja2 Templates, Vanilla JavaScript, CSS3
- Auth       : Flask-Login with role-based session persistence
- Hosting    : Render (Web Service + PostgreSQL 18)
- Deployment : teams-7g57.onrender.com

INSTALLATION & SETUP
--------------------
1. INSTALL DEPENDENCIES:
   pip install flask psycopg2-binary flask-login werkzeug

2. DATABASE CONFIGURATION:
   Ensure DATABASE_URL is set in your environment variables:
   Example: postgresql://user:password@localhost:5432/Teams
   
   For Render deployment: Database URL is automatically configured via
   Render's PostgreSQL service environment variable.

3. RUN THE APPLICATION:
   Local Development:
   python app.py
   Access via http://127.0.0.1:5000
   
   Production (Render):
   Automatic deployment via GitHub integration
   Access via https://teams-7g57.onrender.com

DEPLOYMENT ON RENDER
--------------------
- Web Service : TeamEQ WS (Python 3)
- Database    : TeamsEQ DB (PostgreSQL 18)
- Status      : Deployed and Available
- Free Tier   : Suitable for 0-100 users
- Upgrade Path: $7/month for 1GB RAM (100+ users)
- Auto-Deploy : Enabled via GitHub repository integration

USER ROLES
----------
- GLOBAL ADMIN : Registered using the Master Invite Code. Has full 
                 access to all leagues and system settings.
- LEAGUE ADMIN : Can manage players, generate teams, lock results, 
                 and manage member roles within their specific league.
- READ-ONLY    : Can view standings and rosters but cannot modify data.

DEVELOPMENT NOTES
-----------------
- Results Submission: Integrated into the Standings page. 
- Points Logic: 
    * 12-player games: Total points must equal 12 or 18.
    * 10-player games: Total points must equal 10 or 15.
- Security: Sessions are configured with 'Lax' SameSite cookies and a 
            30-minute expiration for defensive security.

PRODUCTION URLS
---------------
- Live Application : https://teams-7g57.onrender.com
- Privacy Policy   : https://teams-7g57.onrender.com/privacy
- Account Deletion : https://teams-7g57.onrender.com/delete-account
- Manifest (PWA)   : https://teams-7g57.onrender.com/manifest.json

MOBILE APP (ANDROID)
--------------------
- Package Name : com.onrender.teams_7g57.twa
- Distribution : Google Play Store (Closed Testing)
- Build Method : Trusted Web Activity (TWA) via Bubblewrap/PWABuilder
- Play Store   : https://play.google.com/store/apps/details?id=com.onrender.teams_7g57.twa

================================================================================
