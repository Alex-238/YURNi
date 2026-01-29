# Hi — I'm Alex-238 👋
Discord bot developer focused on scalable, production-ready solutions (Slash Commands, background jobs, DB-backed services).  
I build support bots, economy/game systems, and server administration tools with maintainability and observability in mind.

<!-- Badges -->
[![Discord](https://img.shields.io/badge/Discord-Contact-7289DA?logo=discord&logoColor=white)](https://discord.com/users/1348049683096010973)  
![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white) ![discord.js](https://img.shields.io/badge/discord.js-v14-5865F2?logo=discord.js&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?logo=postgresql&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white)

---

## Quick summary
- Role: Discord bot developer (Node.js / discord.js / TypeScript)  
- Approach: clear separation of responsibilities (commands, handlers, services), testable modules, and DB-backed state management  
- Current focus: performance, rate-limiting strategies, UX inside servers, and operational reliability

## Skills & technologies
- Languages / frameworks: Node.js, TypeScript, discord.js (v13 / v14)  
- Datastores & caching: PostgreSQL, Redis (caching & queues)  
- Deployment & ops: Docker, PM2, GitHub Actions (CI/CD), monitoring & logging (Sentry/Logflare)  
- Patterns & practices: Slash commands, context-aware handlers, secure token management, queue-based background jobs

## Typical bot architecture (brief)
- Project structure: commands/ events/ services/ db  
- Register Slash commands via REST during development (guild-scoped) then publish globally when stable  
- Secrets via environment variables (.env) locally or GitHub Secrets in CI  
- Use Redis/queues for long-running tasks, Postgres for persistent data

## Example — /ping command (discord.js v14)
```javascript
// index.js (excerpt)
const { Client, GatewayIntentBits } = require('discord.js');
const client = new Client({ intents: [GatewayIntentBits.Guilds] });

client.on('ready', () => console.log(`Logged in as ${client.user.tag}`));

client.on('interactionCreate', async interaction => {
  if (!interaction.isChatInputCommand()) return;
  if (interaction.commandName === 'ping') {
    await interaction.reply({ content: 'Pong! 🏓', ephemeral: true });
  }
});

client.login(process.env.TOKEN);
```

## Deployment & security (practical)
- Never commit your bot token. Use environment variables or GitHub Secrets.  
- Only enable the gateway intents your bot needs. Request privileged intents in the Discord Developer Portal if required.  
- Containerize with Docker and use a process manager (PM2) or Docker restart policies for resilience.  
- Add monitoring and error tracking (Sentry, Logflare) and health checks.  
- Implement unit and integration tests for critical logic and command handlers.

## Stats (optional)
![GitHub stats](https://github-readme-stats.vercel.app/api?username=Alex-238&show_icons=true&theme=radical)  
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Alex-238&layout=compact&theme=radical)

---

## Contact
- Discord: [Send a direct message](https://discord.com/users/1348049683096010973)  
- Email: [filixyurni@gmail.com](mailto:filixyurni@gmail.com)  
- GitHub: [@Alex-238](https://github.com/Alex-238)

---

## ALGATO 
