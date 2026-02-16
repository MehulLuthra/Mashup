# YouTube Mashup Web Service

A professional web application that creates YouTube audio mashups with a stunning black & white interface.

## 🎨 Features

- ✨ **Bold Black & White Design** with animations
- 🎵 **Background Music Player**
- 📊 **Visitor Counter** (localStorage)
- 📥 **Pre-made Mashup Downloads**
- 📧 **Email Delivery** of custom mashups
- 🎭 **Particle Animation Background**
- 📱 **Fully Responsive**

## 🌐 Best Free Deployment: **Render.com** ✅

**Why Render over Vercel?**
- ✅ No timeout limits (Vercel has 10s limit)
- ✅ Free tier with 750 hours/month
- ✅ Supports long-running processes
- ✅ Built-in ffmpeg support
- ✅ Perfect for this mashup app

## 🚀 Deploy to Render

### Step 1: Create GitHub Repository

```bash
cd /Users/Mehul/Downloads/kag3/mashup
git init
git add .
git commit -m "Initial commit"
git remote add origin YOUR_GITHUB_REPO_URL
git push -u origin main
```

### Step 2: Deploy on Render

1. Go to [render.com](https://render.com) and sign up
2. Click **"New +"** → **"Web Service"**
3. Connect your GitHub repository
4. Configure:
   - **Name**: `mashup-generator`
   - **Environment**: `Python 3`
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app`
   - **Plan**: **Free**

5. Click **"Create Web Service"**

### Step 3: Add Environment Variables

In Render Dashboard → Environment:

```
MAIL_USERNAME=your-email@gmail.com
MAIL_PASSWORD=your-16-char-app-password
MAIL_SERVER=smtp.gmail.com
MAIL_PORT=587
```

### Step 4: Deploy!

Render will auto-deploy. Your app will be live at:
```
https://mashup-generator-xxxx.onrender.com
```

## 📧 Gmail App Password Setup

1. Go to https://myaccount.google.com/security
2. Enable **2-Factor Authentication**
3. Go to **"App Passwords"**
4. Generate password for **"Mail"**
5. Copy the 16-character password
6. Use in `MAIL_PASSWORD` environment variable

## 💻 Local Development

```bash
cd mashup
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Create .env file
cp .env.example .env
# Add your Gmail credentials

# Run
python app.py
```

Open: http://localhost:5000

## 🎵 Add Pre-made Mashups

Put your created mashups in the root directory:
- `bollywood_mashup.mp3` ✅ (already there)
- `arijit_mashup.mp3`
- `atif_mashup.mp3`

Update `PREMADE_MASHUPS` in [app.py](app.py) to add more singers.

## 📱 How to Use

### Create Custom Mashup:
1. Enter singer name
2. Number of videos (must be > 10)
3. Duration in seconds (must be > 20)
4. Your email address
5. Click **"GENERATE MASHUP"**
6. Wait 5-10 minutes
7. Check your email for mashup.zip

### Download Pre-made Mashups:
- Click on any mashup from the list
- Downloads instantly

## ⚠️ Platform Comparison

| Platform | Timeout | Free Tier | Verdict |
|----------|---------|-----------|---------|
| **Render** | None ✅ | 750 hrs/mo | ✅ **BEST** |
| **Railway** | None ✅ | $5 credit/mo | ✅ Good |
| **Vercel** | 10s ❌ | Unlimited | ❌ Too short |

**Vercel is NOT suitable** because mashup creation takes 5-10 minutes, but Vercel has a 10-second timeout.

## 📁 Project Structure

```
mashup/
├── app.py                    # Flask application
├── index.html               # Black & white UI
├── 102317146.py            # CLI script
├── Procfile                # Render config
├── runtime.txt             # Python 3.11
├── requirements.txt        # Dependencies
├── bollywood_mashup.mp3   # Pre-made mashup
└── .env.example           # Environment template
```

## 🎨 Interface Features

**Design:**
- Bold black & white theme
- Gradient background animation
- 50 floating particles
- Shimmer logo effect
- Smooth transitions

**Functionality:**
- Background music player
- Visitor counter
- Mashup creation stats
- Download pre-made mashups
- Real-time form validation

## 🛠️ Troubleshooting

**Email not sending:**
- Verify Gmail App Password
- Check 2FA is enabled
- Look in spam folder

**Timeout errors:**
- Should not happen on Render
- If it does, reduce video count

**Download not working:**
- Ensure mashup file exists
- Check file path in `PREMADE_MASHUPS`

## 👨‍💻 Author

**Mehul Luthra**  
Roll No: 102317146  
Thapar Institute of Engineering & Technology

## 📄 License

MIT License
