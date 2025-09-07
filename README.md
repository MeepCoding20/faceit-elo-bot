# CS2 FACEIT ELO Discord Bot

A Discord bot that automatically assigns FACEIT ELO and level roles based on CS2 statistics.

## Features

- 🎯 **Automatic Role Assignment**: Assigns ELO-specific roles and FACEIT level roles
- 🎨 **Official FACEIT Colors**: Uses authentic FACEIT level colors
- 🔄 **Smart Role Management**: Removes old roles when ELO changes
- 🛡️ **Role-Based Permissions**: Configurable user access control
- 📊 **Comprehensive Logging**: Structured logging with Winston
- 🔁 **Retry Logic**: Robust API error handling with exponential backoff
- 📝 **Case-Insensitive**: Tries multiple username variations

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd cs2-faceit-elo-bot
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   ```bash
   cp .env.example .env
   # Edit .env with your credentials
   ```

4. **Generate Level Roles**
   ```bash
   npm run setup
   ```

5. **Start the bot**
   ```bash
   npm start
   ```

## Configuration

### Environment Variables

Create a `.env` file with the following variables:

```env
DISCORD_TOKEN=your_discord_bot_token
FACEIT_API_KEY=your_faceit_api_key
GUILD_ID=your_discord_server_id
```

### Bot Permissions

The bot requires the following Discord permissions:
- Send Messages
- Read Messages
- Manage Roles
- Read Message History

### Role Configuration

Edit `src/config/config.js` to customize:
- Allowed role name for bot usage
- Command prefix
- Cache settings

## Usage

### Commands

- `!elo <username>` - Updates your Discord role based on FACEIT ELO

### User Permissions

By default, only users with the "ELO Bot User" role can use the bot commands. This can be configured in the config file.

## Project Structure

```
cs2-faceit-elo-bot/
├── src/
│   ├── bot/           # Main bot logic
│   ├── config/        # Configuration files
│   ├── services/      # Business logic services
│   └── utils/         # Utility functions
├── scripts/           # Utility scripts
├── logs/             # Log files
├── .env              # Environment variables
└── package.json      # Project configuration
```

## FACEIT Level System

| Level | Color | ELO Range |
|-------|-------|-----------|
| 1 | Gray | 0-500 |
| 2-3 | Green | 501-900 |
| 4-7 | Gold | 901-1750 |
| 8-9 | Orange | 1531-2000 |
| 10 | Red | 2001+ |

## Scripts

- `npm start` - Start the bot
- `npm run dev` - Start with debugging
- `npm run setup` - Generate all FACEIT level roles
- `npm run fix-colors` - Fix any incorrect role colors
- `npm run logs` - View live logs

## Logging

Logs are stored in the `logs/` directory:
- `combined.log` - All log levels
- `error.log` - Error logs only

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

MIT License - see LICENSE file for details

## Support

For support, please open an issue on GitHub or contact the maintainer.
