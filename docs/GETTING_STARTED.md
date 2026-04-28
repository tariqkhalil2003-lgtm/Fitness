# FitFlow - Getting Started

## 📱 What is FitFlow?

FitFlow is an AI-powered fitness application designed to help you achieve your health and fitness goals. Whether you're a beginner starting your fitness journey or an experienced athlete looking to optimize your performance, FitFlow has personalized workouts, real-time tracking, and community support tailored for you.

## 🚀 Quick Links

- **[Main README](../README.md)** - Project overview
- **[Architecture](ARCHITECTURE.md)** - System design
- **[Roadmap](../ROADMAP.md)** - Development timeline
- **[Contributing](../CONTRIBUTING.md)** - How to contribute
- **[Backend Setup](../backend/SETUP.md)** - Backend development

---

## 🎯 Features

### Free Tier
✅ 200+ exercises with video guides  
✅ Basic workout plans  
✅ Progress tracking  
✅ Workout timer  
✅ Community challenges  
✅ Ad-supported experience  

### Premium Tier ($9.99/month)
✨ Personalized AI coach  
✨ Advanced analytics  
✨ Custom meal plans  
✨ Ad-free experience  
✨ Priority support  
✨ Exclusive workouts  

---

## 🛠 Development Setup

### For Backend Developers

```bash
# Navigate to backend
cd backend

# Install dependencies
npm install

# Setup environment
cp .env.example .env

# Start development server
npm run dev

# Server runs on http://localhost:3000
```

**Requirements:**
- Node.js 18+
- PostgreSQL 12+
- Redis 6+

### For Android Developers

```bash
# Navigate to Android folder
cd android

# Build the project
./gradlew build

# Run on emulator/device
./gradlew installDebug
```

**Requirements:**
- Android Studio Flamingo+
- JDK 11+
- Kotlin 1.9+

---

## 📚 Key Concepts

### Architecture
FitFlow uses a **modular monolith** pattern with:
- **Frontend**: Android (Kotlin) + iOS (Swift - coming soon)
- **Backend**: Node.js + Express
- **Database**: PostgreSQL
- **Cache**: Redis
- **Auth**: JWT + Firebase

### Monetization
Three revenue streams:
1. **Subscriptions** (60%) - Premium features
2. **Ads** (30%) - Free tier monetization
3. **Affiliate** (10%) - Product partnerships

### Target Metrics
| Metric | Target | Timeline |
|--------|--------|----------|
| Users | 50K → 1M+ | Year 1-3 |
| Revenue | $5K → $500K+/month | Year 1-3 |
| Retention (30-day) | 40% → 60% | Year 1-3 |
| App Rating | 4.5⭐ | Always |

---

## 🔐 Authentication

### Sign Up Flow
```
1. User enters email + password
2. Server validates input
3. Password hashed with bcrypt
4. User created in database
5. JWT token issued
6. Profile creation screen shown
```

### Login Flow
```
1. User enters credentials
2. Server validates password
3. JWT token issued + refresh token saved
4. User directed to home screen
5. Token refreshed automatically before expiry
```

---

## 📝 API Overview

### Base URL
```
Development: http://localhost:3000/api/v1
Production: https://api.fitflow.app/api/v1
```

### Authentication Header
```
Authorization: Bearer <your_jwt_token>
```

### Example Request
```bash
curl -X GET http://localhost:3000/api/v1/workouts \
  -H "Authorization: Bearer your_token_here"
```

---

## 🧪 Testing

### Run Tests
```bash
# Backend tests
cd backend && npm test

# Android tests
cd android && ./gradlew test

# With coverage
npm test -- --coverage
```

### Write Tests
Each feature should have:
- ✅ Unit tests for business logic
- ✅ Integration tests for API endpoints
- ✅ E2E tests for critical flows

---

## 📊 Database

### Key Tables
- `users` - User accounts
- `workouts` - Workout programs
- `exercises` - Exercise library
- `user_progress` - Progress tracking
- `subscriptions` - Premium status

### Running Migrations
```bash
cd backend
npm run db:migrate
npm run db:seed  # Add sample data
```

---

## 🚢 Deployment

### Staging
Automatic deployment on push to `develop` branch

### Production
Automatic deployment on push to `main` branch

### Manual Deploy
```bash
# Build Docker image
docker build -t fitflow:latest .

# Push to registry
docker push your-registry/fitflow:latest

# Deploy
kubectl apply -f k8s/
```

---

## 🐛 Common Issues

### "Cannot connect to database"
```bash
# Check PostgreSQL is running
pg_isready

# Verify .env has correct DB credentials
cat .env | grep DB_
```

### "Port 3000 already in use"
```bash
# Find and kill process
lsof -i :3000
kill -9 <PID>
```

### "JWT token expired"
```
Solution: User needs to login again to get fresh token
The app handles this automatically
```

---

## 📚 Learning Resources

### Documentation
- [Kotlin Docs](https://kotlinlang.org/docs)
- [Express.js Guide](https://expressjs.com)
- [PostgreSQL Docs](https://www.postgresql.org/docs)
- [Firebase Docs](https://firebase.google.com/docs)

### Firebase Setup
1. Go to [Firebase Console](https://console.firebase.google.com)
2. Create new project
3. Add Android app
4. Download `google-services.json`
5. Copy to `android/app/`

### Stripe Setup
1. Create [Stripe Account](https://stripe.com)
2. Get API keys
3. Add to `.env` (backend)
4. Test with card: `4242 4242 4242 4242`

---

## 💬 Communication

### Team Channels
- **Slack**: #fitflow-dev
- **Email**: team@fitflow.app
- **GitHub Issues**: For bugs and features
- **Discord**: Community chat

### Meetings
- **Weekly Standup**: Monday 10 AM
- **Sprint Planning**: Every other Friday
- **Code Review**: Continuous on PRs

---

## 🎓 Code Standards

### Branch Naming
```
feature/amazing-feature
bugfix/fix-login-issue
docs/api-documentation
```

### Commit Messages
```
✨ Add new feature
🐛 Fix bug in authentication
📚 Update documentation
⚡ Improve performance
🔒 Add security validation
```

### Pull Requests
- Describe changes clearly
- Link to related issues
- Request review from 2+ team members
- Ensure all checks pass
- Minimum 80% code coverage

---

## 📈 Success Metrics

We measure success by:
- **User Acquisition**: Downloads and signups
- **Engagement**: Daily/Monthly active users
- **Retention**: % of users coming back
- **Monetization**: Revenue per user
- **Quality**: App rating and crash rate

---

## 🎓 Next Steps

1. **Setup Development Environment**
   - Clone the repo
   - Install dependencies
   - Configure environment

2. **Explore the Code**
   - Check out the architecture
   - Review existing features
   - Understand the patterns

3. **Pick a Task**
   - Check GitHub Issues
   - Start with "good first issue"
   - Ask for help if needed

4. **Make Your First Contribution**
   - Create a feature branch
   - Make changes
   - Submit a PR
   - Get reviewed

---

## 🤝 Need Help?

- **Documentation**: Check this guide first
- **Issues**: Search GitHub Issues
- **Team**: Post in #fitflow-dev Slack
- **Email**: support@fitflow.app

---

**Welcome to FitFlow! Let's build something amazing together.** 💪🚀
