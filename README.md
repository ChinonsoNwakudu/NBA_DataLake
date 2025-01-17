# 🏀 NBA Data Lake Project

Turn your basketball data into insights! This project sets up a fully automated data lake for NBA analytics using AWS services. Whether you're analyzing player stats, tracking team performance, or just love swimming in basketball data, we've got you covered.

## 🎯 What's This All About?

Ever wondered how to store and analyze NBA data like the pros? This project creates a serverless data lake that automatically:
- Fetches fresh NBA data from SportsData.io
- Stores it in a well-organized S3 bucket
- Sets up queryable tables using AWS Glue
- Makes it all easily accessible through Amazon Athena

## 🛠️ Tech Stack

We're running on AWS because we like our data lakes as reliable as Kareem's skyhook:
- Amazon S3 for data storage
- AWS Glue for data cataloging
- Amazon Athena for SQL queries
- Python for automation
- SportsData.io API for NBA stats

## 🚀 Getting Started

### First Things First
1. **Get Your API Key**
   - Create a free account at SportsData.io
   - Hover over "Developers" and click "API Resources"
   - Follow "Introduction & Testing"
   - Get your NBA API key (we'll need this!)

### Set Up Your AWS Environment
Make sure you've got these AWS permissions ready:
- S3 bucket management
- Glue database/table operations
- Athena query execution

### Quick Setup Guide

1. **Fire Up AWS CloudShell**
   ```bash
   # Open CloudShell from AWS Console (look for the >_ icon)
   ```

2. **Create Your Script**
   ```bash
   nano setup_nba_data_lake.py
   # Copy the script contents from the repository
   # Don't forget to add your API key!
   ```

3. **Set Up Environment Variables**
   ```bash
   nano .env
   ```
   Add these lines (with your actual API key):
   ```
   SPORTS_DATA_API_KEY=your_sportsdata_api_key
   NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players
   ```

4. **Run It!**
   ```bash
   python3 setup_nba_data_lake.py
   ```

## 📊 Sample Queries

Want to find all point guards in the league? Try this in Athena:
```sql
SELECT FirstName, LastName, Position, Team
FROM nba_players
WHERE Position = 'PG';
```

## 🔍 What's Happening Behind the Scenes?

When you run the script, it:
1. Creates an S3 bucket for your data
2. Sets up a Glue database and table structure
3. Configures Athena for querying
4. Fetches and loads initial NBA data
5. Makes everything ready for analysis

## 🤔 Common Questions

**Q: How often is the data updated?**
A: Currently manual, but you can schedule regular updates using AWS EventBridge!

**Q: Can I analyze historical data?**
A: Absolutely! Just modify the API endpoint in your .env file.



## 📫 Need Help?

If you're stuck or have questions:
- Open an issue on GitHub
- Check AWS documentation for service-specific details
- Review SportsData.io API docs for data questions

---

