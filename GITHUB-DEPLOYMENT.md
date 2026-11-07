# GitHub Deployment Guide - Legacy Wealth

Deploy your Legacy Wealth trading platform **FREE** using GitHub and a cloud hosting service.

## Quick Start (3 Steps)

### Step 1: Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Create repository: `legacywealth` (or your preferred name)
3. Clone the repo locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/legacywealth.git
   cd legacywealth
   ```

4. Copy all files from this project into the repository folder
5. Push to GitHub:
   ```bash
   git add .
   git commit -m "Initial commit: Legacy Wealth platform"
   git push origin main
   ```

---

## Step 2: Set Up Database (PostgreSQL)

You'll need a free PostgreSQL database. Choose one:

### Option A: ElephantSQL (Recommended - Easiest)
1. Go to [elephantsql.com](https://www.elephantsql.com)
2. Sign up (free account)
3. Create a new instance (Tiny Turtle free tier)
4. Copy the **URL** (looks like: `postgres://user:pass@host/db`)
5. Save this for deployment configuration

### Option B: Render PostgreSQL
1. Go to [render.com](https://render.com)
2. Create account
3. Create PostgreSQL database (free tier available)
4. Copy connection string

---

## Step 3: Deploy Using Render (FREE)

Render offers free tier hosting perfect for this app!

### Create Account & Deploy

1. Go to [render.com](https://render.com)
2. Sign up with GitHub account
3. Click **"New +"** → **"Web Service"**
4. Connect your GitHub repo
5. Fill in settings:
   - **Name**: `legacywealth`
   - **Environment**: `Python 3`
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app`
   - **Instance Type**: `Free`

### Add Environment Variables

In Render dashboard, go to **Environment** and add:

```
DATABASE_URL=postgres://user:pass@host/db
SECRET_KEY=your-secret-key-here
BINANCE_API_KEY=(optional)
BINANCE_API_SECRET=(optional)
WALLET_TRC20=(your-wallet-address)
WALLET_BEP20=(your-wallet-address)
WALLET_ERC20=(your-wallet-address)
MPESA_CONSUMER_KEY=(if-using-mpesa)
MPESA_CONSUMER_SECRET=(if-using-mpesa)
MPESA_PASSKEY=(if-using-mpesa)
```

6. Click **Create Web Service**
7. Wait 5-10 minutes for deployment
8. Your app will be live at: `https://legacywealth.onrender.com`

---

## Alternative: Railway.app (Also Free)

Railway is another excellent free option:

1. Go to [railway.app](https://railway.app)
2. Sign in with GitHub
3. Create new project
4. Add PostgreSQL database from marketplace
5. Add web service from GitHub repo
6. Set environment variables
7. Deploy!

Your app will be live in minutes.

---

## Testing Your Deployment

Once deployed:

1. Visit: `https://your-app-name.onrender.com`
2. Go to `/login`
3. Test accounts:
   - **Client**: john@test.com / demo1234
   - **Admin**: admin@test.com / admin1234

---

## Keep Your App Running (Free Tier Tips)

- Render's free tier puts apps to sleep after 15 min of inactivity
- To keep running 24/7, upgrade to **Paid tier** ($7/month)
- Or use [UptimeRobot.com](https://uptimerobot.com) (free) to ping your app periodically

---

## Features

✅ 10% Daily Return on Deposits  
✅ 12.5% Referral Bonus  
✅ 8 Deposit Packages ($2.5K - $10K)  
✅ No Minimum Withdrawal  
✅ White & Green Theme  
✅ Admin Dashboard  
✅ M-Pesa Integration (Optional)  
✅ Referral System  
✅ Trading Simulator  

---

## Support

Need help? Check:
- `DEPLOYMENT.md` - Detailed deployment info
- `QUICKSTART.md` - Getting started guide
- `README.md` - Full documentation

---

## Security Notes

⚠️ **Important**:
- Change `SECRET_KEY` in environment variables
- Keep `DATABASE_URL` secret (never commit)
- Use strong passwords for admin accounts
- Enable HTTPS (Render does this automatically)
- Consider adding 2FA for admin accounts

---

**Happy Deploying!** 🚀
