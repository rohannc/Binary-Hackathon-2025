# The Eleven - Fantasy Cricket with Crypto

A fantasy cricket application built for the "Binary" hackathon organized by Kalyani Government Engineering College, Kalyani.

## Overview

The Eleven is a revolutionary fantasy cricket platform that combines the excitement of fantasy sports with cryptocurrency transactions. Users can join various contests (free or paid, multiplayer or single-player), select players based on their performance metrics, and compete for crypto rewards.

## Unique Features

- **Crypto Integration**: Decentralized payment system using cryptocurrencies instead of real money
- **AI-Powered Player Valuation**: Base credit calculation using Gemma AI model based on player performance
- **Data-Driven Decisions**: Player stats from recent 10 matches web-scraped and analyzed

## How It Works

1. **Create an Account**: Sign up and link your crypto wallet
2. **Join Contests**: Enter various contests with your crypto balance
3. **Build Your Team**: Select 11 players within your credit limit
4. **Choose Captain & Vice-Captain**: Special players who can multiply your points
5. **Track Live Performance**: Watch as your players earn points based on real-time match performance
6. **Win Crypto**: Winners receive payouts directly to their linked wallets

## Technical Implementation

### Base Credit Calculation System (This Repository)

This repository contains the backend logic for player credit valuation, featuring:

- **Web Scraping Pipeline**: Extracts recent player performance data from cricket websites
- **Database Architecture**: 
  - MongoDB for storing web scraping URLs
  - SQLite Cloud for player performance data and calculated credit points
- **AI Valuation Model**: Gemma AI analyzes player statistics to calculate fair credit values
- **REST API**: Flask-powered endpoints to serve player data
- **Fuzzy Matching**: FuzzyWuzzy implementation for partial player name matching in API calls

### System Architecture

```
Web Sources → Web Scraper → MongoDB (URLs) → SQLite Cloud (Player Data) → 
Gemma AI (Credit Calculation) → SQLite Cloud (Credit Points) → 
Flask API → Frontend Application
```

## API Usage

Access player data through our REST API:

```
GET /api/player/{player_name}
```

Returns player credit information in JSON format:

```json
{
  "player_name": "Virat Kohli",
  "base_credit": 10.5,
  "recent_form": "Good",
  "last_updated": "2025-03-25"
}
```

## Team & Related Repositories

This project was developed as a team effort for the "Binary" hackathon. Visit our team members' repositories for other components:

- [Bijit Mondal](https://github.com/Bijit-Mondal/Gamed-Backend)
- [Soumyodeep Das](https://github.com/Soumyodeep-Das)
- [Sayantan Ghosh](https://github.com/stravo1/binary-web3)

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/the-eleven.git

# Navigate to project directory
cd the-eleven

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your configuration

# Run the application
python app.py
```

## Future Enhancements

- Integration with additional crypto wallets
- Expanded player database
- Advanced statistical models for credit calculation
- Mobile application


## Acknowledgments

Special thanks to Kalyani Government Engineering College for organizing the "Binary" hackathon that made this project possible.
