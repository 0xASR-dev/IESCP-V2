# 🌟 IESCP - Influencer Engagement & Sponsor Coordination Platform

<div align="center">

![Platform](https://img.shields.io/badge/Platform-Web-blue)
![Framework](https://img.shields.io/badge/Framework-Flask-green)
![Database](https://img.shields.io/badge/Database-SQLite-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Status-Active-success)

**A modern web platform connecting brands with influencers for authentic partnerships and campaign management.**

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [API Routes](#-api-routes) • [Contributing](#-contributing)

</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Database Schema](#-database-schema)
- [API Routes](#-api-routes)
- [User Roles](#-user-roles)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 About

**IESCP (Influencer Engagement & Sponsor Coordination Platform)** is a comprehensive web application designed to bridge the gap between brands (sponsors) and content creators (influencers). The platform facilitates seamless collaboration, campaign management, and ad request workflows.

### Why IESCP?

- 🎯 **Smart Matching**: Connect sponsors with the perfect influencers based on niche and reach
- 📊 **Campaign Analytics**: Track campaign progress and performance metrics
- 💼 **Streamlined Management**: Centralized dashboard for all stakeholders
- 🔒 **Secure Platform**: Role-based access control and data protection
- 💬 **Easy Communication**: Built-in ad request and negotiation system

---

## ✨ Features

### For Sponsors
- ✅ Create and manage advertising campaigns
- ✅ Search and filter influencers by category, niche, and reach
- ✅ Send ad requests to influencers
- ✅ Track campaign progress and budget utilization
- ✅ Manage multiple campaigns simultaneously
- ✅ Public and private campaign visibility options

### For Influencers
- ✅ Browse available public campaigns
- ✅ Receive and manage ad requests from sponsors
- ✅ Accept, reject, or negotiate ad requests
- ✅ Track completed ads and earnings
- ✅ Profile management with reach statistics
- ✅ Campaign discovery based on niche

### For Admins
- ✅ User management (flag/unflag users)
- ✅ Campaign moderation (flag/unflag campaigns)
- ✅ Platform statistics and analytics dashboard
- ✅ Handle unflag requests from users
- ✅ Delete inappropriate users or campaigns
- ✅ Complete platform oversight

---

## 🛠️ Tech Stack

### Backend
- **Framework**: Flask 3.0.3
- **ORM**: SQLAlchemy 2.0.31
- **Database**: SQLite (Development)
- **Authentication**: Flask-Login 0.6.3
- **Migrations**: Flask-Migrate 4.0.7

### Frontend
- **Template Engine**: Jinja2 3.1.4
- **CSS Framework**: Bootstrap 5.3.3
- **Icons**: Emoji-based icons
- **Animations**: Custom CSS3 animations

### Development Tools
- **Python**: 3.11+
- **Package Manager**: pip
- **Version Control**: Git

---

## 🚀 Installation

### Prerequisites

- Python 3.11 or higher
- pip (Python package manager)
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/22f3002042/IESC-platform.git
cd IESC-platform
```

### Step 2: Create Virtual Environment (Recommended)

**Windows:**
```powershell
python -m venv venv
.\venv\Scripts\activate
```

**macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirement.txt
```

### Step 4: Initialize Database

```python
# Run Python interactive shell
python

# Execute the following commands
>>> from main import app, db
>>> with app.app_context():
...     db.create_all()
>>> exit()
```

### Step 5: Run the Application

```bash
python main.py
```

The application will be available at `http://localhost:5000/`

---

## 📖 Usage

### First-Time Setup

1. **Access the Landing Page**: Navigate to `http://localhost:5000/`
2. **Admin Access**: Use admin credentials to access the admin panel
3. **Register as Sponsor**: Click "Sign Up" under the Sponsor card
4. **Register as Influencer**: Click "Sign Up" under the Influencer card

### Default Admin Credentials

Create an admin user manually in the database or through the app initialization:
- **Email**: admin@gmail.com
- **Password**: admin123
- **Role**: admin

### Sponsor Workflow

1. **Sign Up**: Register with company details, industry, and budget
2. **Create Campaign**: Set up campaigns with goals, budget, and visibility
3. **Find Influencers**: Search for influencers by category, niche, and reach
4. **Send Ad Requests**: Send personalized ad requests with payment details
5. **Track Progress**: Monitor campaign progress and ad completion

### Influencer Workflow

1. **Sign Up**: Register with category, niche, and reach information
2. **Browse Campaigns**: Explore public campaigns matching your niche
3. **Manage Requests**: Review incoming ad requests from sponsors
4. **Accept/Reject**: Decide on ad requests based on your preferences
5. **Track Earnings**: Monitor completed ads and payment amounts

### Admin Workflow

1. **Login**: Access admin dashboard
2. **Monitor Users**: View all users, flag/unflag inappropriate accounts
3. **Moderate Campaigns**: Review and flag campaigns violating policies
4. **Handle Requests**: Approve or reject unflag requests from users
5. **Analytics**: View platform statistics and trends

---

## 📁 Project Structure

```
IESC-platform/
│
├── instance/
│   └── iesc.db                 # SQLite database file
│
├── templates/                  # HTML templates
│   ├── base.html              # Base template with navbar
│   ├── home.html              # Landing page
│   ├── login.html             # Login page
│   │
│   ├── admin/                 # Admin templates
│   │   ├── admin_dash.html
│   │   ├── admin_profile.html
│   │   └── manage_users.html
│   │
│   ├── campaigns/             # Campaign templates
│   │   ├── admin_cam/
│   │   ├── influencer_cam/
│   │   └── sponsor_cam/
│   │
│   ├── influencer/            # Influencer templates
│   │   ├── influencer_dash.html
│   │   ├── influencer_profile.html
│   │   └── influencer_signup.html
│   │
│   └── sponsor/               # Sponsor templates
│       ├── sponsor_dash.html
│       ├── sponsor_profile.html
│       └── sponsor_signup.html
│
├── __pycache__/               # Python cache files
│
├── main.py                    # Main application file with routes
├── models.py                  # Database models (User, Campaign, AdRequest)
├── db.py                      # Database initialization
├── requirement.txt            # Project dependencies
├── README.md                  # Project documentation (this file)
├── DESIGN_UPDATES.md          # Design documentation
├── PREVIEW_GUIDE.md           # Preview guide
└── BEFORE_AFTER.md            # Design comparison
```

---

## 🗄️ Database Schema

### Users Table
```python
- id (Primary Key)
- username (Unique, Required)
- email (Unique, Required)
- password (Required)
- role (admin/sponsor/influencer)
- flagged (Boolean, default: False)
- unflag_request (Text)

# Sponsor-specific fields
- company_name
- industry
- budget

# Influencer-specific fields
- category
- niche
- reach (followers/subscribers count)
```

### Campaigns Table
```python
- id (Primary Key)
- title (Required)
- description (Required)
- niche (Required)
- start_date (Date)
- end_date (Date)
- budget (Float)
- visibility (public/private)
- status (active/completed)
- goals (Text)
- sponsor_id (Foreign Key -> Users)
- is_flagged (Boolean, default: False)
```

### AdRequests Table
```python
- id (Primary Key)
- campaign_id (Foreign Key -> Campaigns)
- influencer_id (Foreign Key -> Users)
- sponsor_id (Foreign Key -> Users)
- details (Text)
- payment_amount (Float)
- status (Pending/Accepted/Rejected/Completed)
- ads_required (Integer)
- ads_completed (Integer)
- updated_at (DateTime)
```

### Relationships
- One Sponsor → Many Campaigns
- One Campaign → Many AdRequests
- One Influencer → Many AdRequests
- Cascading deletes for data integrity

---

## 🛣️ API Routes

### Public Routes
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/` | Redirect to home |
| GET | `/home` | Landing page |
| GET/POST | `/login` | User login |
| GET/POST | `/sponsor_signup` | Sponsor registration |
| GET/POST | `/influencer_signup` | Influencer registration |
| GET | `/logout` | User logout |

### Admin Routes
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/admin_profile` | Admin profile page |
| POST | `/admin/edit_admin_profile` | Update admin profile |
| GET | `/admin_dash` | Admin dashboard with statistics |
| GET | `/admin/manage_users` | User management panel |
| POST | `/admin/users/flag/<user_id>` | Flag a user |
| POST | `/admin/users/unflag/<user_id>` | Unflag a user |
| POST | `/admin/users/delete/<user_id>` | Delete a user |
| GET | `/admin/unflag_requests` | View unflag requests |
| POST | `/admin/approve_unflag/<user_id>` | Approve unflag request |
| GET | `/admin/campaigns` | Campaign management |
| POST | `/admin/campaigns/flag/<campaign_id>` | Flag a campaign |
| POST | `/admin/flagged_campaigns/unflag/<campaign_id>` | Unflag campaign |
| POST | `/admin/flagged_campaigns/delete/<campaign_id>` | Delete campaign |

### Sponsor Routes
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/sponsor_profile` | Sponsor profile page |
| POST | `/sponsor_profile/edit` | Update sponsor profile |
| GET | `/sponsor_dash` | Sponsor dashboard |
| GET | `/sponsor_campaigns` | View sponsor campaigns |
| POST | `/sponsor/campaigns/create` | Create new campaign |
| POST | `/sponsor/campaigns/edit/<campaign_id>` | Update campaign |
| POST | `/sponsor/campaigns/delete/<campaign_id>` | Delete campaign |
| GET | `/sponsor/campaigns/view/<campaign_id>` | View campaign details |
| GET | `/sponsor/search_influencers` | Search influencers |
| GET | `/sponsor/ad_requests` | Manage ad requests |
| POST | `/sponsor/ad_requests/create` | Create ad request |

### Influencer Routes
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/influencer_profile` | Influencer profile page |
| POST | `/influencer_profile/edit` | Update influencer profile |
| GET | `/influencer_dash` | Influencer dashboard |
| GET | `/influencer/public_campaigns` | Browse public campaigns |
| GET | `/influencer/campaigns/<campaign_id>` | View campaign details |
| GET | `/influencer/ad_requests` | Manage ad requests |
| POST | `/influencer/ad_requests/<request_id>/accept` | Accept ad request |
| POST | `/influencer/ad_requests/<request_id>/reject` | Reject ad request |
| POST | `/influencer/ad_requests/<request_id>/complete` | Mark ad completed |

---

## 👥 User Roles

### 🔱 Admin
- **Access Level**: Full platform access
- **Capabilities**: User management, content moderation, analytics
- **Restrictions**: Cannot create campaigns or ad requests
- **Dashboard**: Platform-wide statistics and management tools

### 💼 Sponsor
- **Access Level**: Campaign and influencer management
- **Capabilities**: Create campaigns, search influencers, send ad requests
- **Restrictions**: Cannot access admin features
- **Dashboard**: Campaign performance and ad request tracking

### ⭐ Influencer
- **Access Level**: Campaign browsing and ad request management
- **Capabilities**: Browse campaigns, accept/reject requests, track earnings
- **Restrictions**: Cannot create campaigns
- **Dashboard**: Ad request status and earnings overview

---

## 📸 Screenshots

### Landing Page
Modern gradient design with animated elements and clear CTAs.

### Dashboard Views
- **Admin Dashboard**: User statistics, campaign overview, flagged content
- **Sponsor Dashboard**: Campaign metrics, budget tracking, influencer reach
- **Influencer Dashboard**: Pending requests, completed ads, earnings

### Campaign Management
- Create/Edit campaigns with rich details
- Public/Private visibility options
- Progress tracking with percentage completion

### Ad Request System
- Detailed request forms
- Status tracking (Pending/Accepted/Rejected/Completed)
- Payment amount negotiation

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
```bash
git clone https://github.com/22f3002042/IESC-platform.git
```

2. **Create a feature branch**
```bash
git checkout -b feature/YourFeatureName
```

3. **Commit your changes**
```bash
git commit -m "Add: Your feature description"
```

4. **Push to the branch**
```bash
git push origin feature/YourFeatureName
```

5. **Open a Pull Request**

### Coding Standards
- Follow PEP 8 style guide for Python code
- Use meaningful variable and function names
- Add comments for complex logic
- Write docstrings for functions and classes
- Test thoroughly before submitting PR

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 IESCP

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

---

## 📧 Contact

### Project Maintainer
- **GitHub**: [@22f3002042](https://github.com/22f3002042)
- **Repository**: [IESC-platform](https://github.com/22f3002042/IESC-platform)

### Support
- **Issues**: [GitHub Issues](https://github.com/22f3002042/IESC-platform/issues)
- **Discussions**: [GitHub Discussions](https://github.com/22f3002042/IESC-platform/discussions)

---

## 🎉 Acknowledgments

- **Flask**: For the amazing web framework
- **Bootstrap**: For responsive UI components
- **SQLAlchemy**: For elegant database management
- **Contributors**: Thanks to all contributors who help improve this project

---

## 🔄 Version History

### v1.0.0 (Current)
- ✅ Initial release
- ✅ Core functionality for all three user roles
- ✅ Campaign and ad request management
- ✅ Modern responsive UI with animations
- ✅ Admin moderation tools
- ✅ User flag/unflag system

### Upcoming Features
- 🔜 Real-time notifications
- 🔜 Advanced analytics and reporting
- 🔜 Payment gateway integration
- 🔜 Messaging system between users
- 🔜 Campaign templates
- 🔜 Export data functionality
- 🔜 API for mobile app integration

---

## 📊 Project Stats

![Lines of Code](https://img.shields.io/badge/Lines%20of%20Code-1000%2B-blue)
![Python Version](https://img.shields.io/badge/Python-3.11%2B-green)
![Database](https://img.shields.io/badge/Database-SQLite-orange)
![UI Framework](https://img.shields.io/badge/UI-Bootstrap%205-purple)

---

<div align="center">

**Made with ❤️ for connecting brands and influencers**

⭐ Star this repository if you find it helpful!

[Back to Top](#-iescp---influencer-engagement--sponsor-coordination-platform)

</div>
