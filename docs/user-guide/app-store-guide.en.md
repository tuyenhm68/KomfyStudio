# 🏪 App Store User Guide

**App Store** is a community platform that allows you to discover, install, and share AI applications created by the Komfy Studio community.

---

## 📋 Table of Contents

- [Introduction](#introduction)
- [Accessing App Store](#accessing-app-store)
- [Search & Discovery](#search--discovery)
- [Installing Applications](#installing-applications)
- [Updating Applications](#updating-applications)
- [Managing Installed Apps](#managing-installed-apps)
- [Publishing Applications](#publishing-applications)
- [Tips & Best Practices](#tips--best-practices)
- [Troubleshooting](#troubleshooting)

---

## 🎯 Introduction

App Store provides:

- 🔍 **Discover apps**: Browse through community-created applications
- 📥 **One-click install**: Easy download and installation
- 🔄 **Auto-update**: Get notified when new versions are available
- 🏷️ **Clear categorization**: Search by category and tags
- ⭐ **Ratings & Reviews**: See ratings from other users
- 📤 **Easy sharing**: Publish your apps to the Store

---

## 🚀 Accessing App Store

### Opening App Store

1. Open **Komfy Studio**
2. Click on the **"Store"** tab in the left sidebar (🏪 icon)
3. Or go to **Apps > App Store** in the menu

### App Store Interface

App Store is divided into 3 main areas:

#### 1️⃣ Left Sidebar - Search & Filter

- **Search Bar**: Search apps by name, description
- **Categories**: Filter by category
  - 🎨 **All**: All applications
  - 🖼️ **Image**: Image processing apps
  - 🎬 **Video**: Video processing apps
  - 🎵 **Audio**: Audio processing apps

#### 2️⃣ Top Bar - Backend Status

- Display backend connection status
- Select active backend
- Refresh backend health

#### 3️⃣ Main Content - App List

- Grid layout displaying app cards
- Each card shows:
  - **Icon**: Application icon
  - **Name**: Application name
  - **Author**: App creator
  - **Rating**: Average rating (⭐)
  - **Installs**: Installation count
  - **Status**: Status (Installed, Update Available)
  - **Action Button**: Install/Update/Installed

---

## 🔍 Search & Discovery

### Search by Keyword

1. **Enter keyword** in Search box
2. System searches in:
   - App name
   - Description
   - Tags
   - Author name
3. Results display in real-time

**Example keywords**:
- "portrait" - Find portrait generation apps
- "anime" - Find anime style apps
- "fast" - Find fast generation apps
- "realistic" - Find realistic style apps

### Filter by Category

Click on category in sidebar:

- **All**: Show all applications
- **Image**: Show only image processing apps
- **Video**: Show only video processing apps
- **Audio**: Show only audio processing apps

### Sorting

Sorting options (coming soon):
- **Popular**: By installation count (default)
- **Newest**: By publish time
- **Rating**: By highest rating

---

## 📥 Installing Applications

### Installation Process

#### 1️⃣ Select Application

1. **Find app** you want to install
2. **View information**:
   - Read description
   - Check requirements
   - View rating and install count

#### 2️⃣ Click Install

1. Click **"Install"** button (📥 icon) on app card
2. System begins installation process

#### 3️⃣ Installation Process

System will automatically:

1. **Download .kapp file**:
   - Download package from cloud storage
   - Display progress bar

2. **Extract package**:
   - Unzip .kapp file
   - Read metadata, workflow, UI layout

3. **Validate dependencies**:
   - Check required models
   - Check required custom nodes

4. **Install dependencies** (if missing):
   - **Models**: Auto-download missing models
   - **Custom Nodes**: Auto-install missing nodes
   - Display progress for each item

5. **Save to database**:
   - Save app to local database
   - Save icon (base64) for offline use

6. **Complete**:
   - Display "Installed successfully" notification
   - App appears in **My Apps**
   - Button changes to **"Installed"** (✅)

#### 4️⃣ Using the App

After installation:

1. Go to **Apps > My Apps**
2. Find newly installed app
3. Click on app to open and use

### Dependencies Auto-Install

**Benefits of automatic system**:

- ✅ **No manual intervention**: System auto-downloads and installs
- ✅ **Progress tracking**: Monitor each step
- ✅ **Error handling**: Automatic error handling and retry
- ✅ **Offline support**: Icon and metadata saved offline

**Notes**:

- ⚠️ Installation may take several minutes if large models need downloading
- ⚠️ Ensure sufficient disk space
- ⚠️ Stable internet connection for downloads

---

## 🔄 Updating Applications

### Update Detection

System automatically checks for updates when:

- Opening App Store
- Refreshing app list
- Periodically (background check)

### Update Notification

When new version available:

- **Yellow badge** appears on app card
- Text **"NEW v1.2.0"** (new version)
- Button changes to **"Update"** (🔄 icon)

### Installing Updates

1. **Click "Update" button** on app card
2. System will:
   - Download new version
   - Update metadata
   - Update workflow (if changed)
   - Update UI layout (if changed)
   - Install new dependencies (if any)
3. **Complete**: App updated to new version

### Version Management

- System tracks current version and latest version
- Compare using **Semantic Versioning** standard
- Only show update if new version > current version

**Example**:
- Local: v1.0.0
- Store: v1.2.0
- → Display "Update Available"

---

## 📱 Managing Installed Apps

### View List

Go to **Apps > My Apps** to see:

- All installed apps
- Self-created apps (from App Builder)
- Status of each app

### Distinguish App Types

#### Apps from Store:

- **Source**: "App Store"
- **Can update**: When author releases new version
- **Has publish_id**: Linked to app on Store

#### Self-Created Apps:

- **Source**: "Local"
- **No auto-update**: You manage version yourself
- **Can publish**: To App Store for sharing

### Management Functions

#### ✏️ Edit

- **Self-created apps**: Can edit anytime
- **Apps from Store**: Cannot edit (to preserve original)

#### 🗑️ Uninstall

1. Click **Delete** icon (🗑️)
2. Confirm deletion
3. App will be removed from local database

**Note**:
- Dependencies (models, nodes) are NOT deleted
- Can reinstall from Store anytime

#### 📤 Export

- Export app as `.kapp` file
- Backup or share with others
- Import to another machine

---

## 📤 Publishing Applications

### Who Can Publish?

- Anyone with Komfy Studio account
- Has created app using App Builder
- App is thoroughly tested and working well

### Publishing Process

See details in [App Builder Guide - Publishing Section](app-builder-guide.en.md#publishing-to-app-store)

**Summary**:

1. **Create app** using App Builder
2. **Test thoroughly** in My Apps
3. **Click "Publish"** from My Apps or App Builder
4. **Confirm information**
5. **App appears on Store** immediately

### Benefits of Publishing

- ✅ Share creativity with community
- ✅ Receive feedback from users
- ✅ Track installation count
- ✅ Build reputation in community
- ✅ Contribute to Komfy Studio ecosystem

### Responsibilities

- ⚠️ Ensure app works correctly
- ⚠️ Provide complete, accurate information
- ⚠️ Fully list requirements
- ⚠️ Don't publish apps with inappropriate content
- ⚠️ Respect copyright and original authors

---

## 💡 Tips & Best Practices

### When Searching for Apps

- ✅ Read description carefully before installing
- ✅ Check requirements (models, nodes)
- ✅ View rating and install count
- ✅ Prefer apps with detailed descriptions
- ✅ Check version and update date

### When Installing

- ✅ Ensure sufficient disk space
- ✅ Stable internet connection
- ✅ Wait for installation to complete
- ✅ Read usage instructions (if available)
- ✅ Test app after installation

### When Publishing

- ✅ Test thoroughly before publishing
- ✅ Write clear, detailed description
- ✅ Upload high-quality icon
- ✅ Fully list requirements
- ✅ Choose appropriate category and tags
- ✅ Update version following standards

### Managing Apps

- ✅ Regularly check for updates
- ✅ Uninstall unused apps to save space
- ✅ Backup important apps (Export .kapp)
- ✅ Organize apps by category
- ✅ Rate and review used apps (coming soon)

---

## 🔧 Troubleshooting

### Cannot Connect to App Store

**Symptom**: Cannot load app list

**Solution**:
- Check internet connection
- Verify API endpoint: `https://komfy-admin.pages.dev/api`
- Try refreshing page (Ctrl+R)
- Check if firewall/antivirus is blocking
- View console logs for debugging

### Installation Failed

**Symptom**: Error when installing app

**Solution**:

1. **Download error**:
   - Check internet connection
   - Try again after a few minutes
   - Check disk space

2. **Dependencies error**:
   - Check backend is running
   - Verify models path is correct
   - Try installing dependencies manually
   - View logs to identify problematic dependency

3. **Database error**:
   - Restart application
   - Check file write permissions
   - Clear cache and try again

### App Not Appearing After Installation

**Symptom**: Installation successful but app not visible

**Solution**:
- Refresh My Apps page
- Check "My Apps" tab is selected
- View console logs
- Restart application
- Check if database saved the app

### Update Failed

**Symptom**: Cannot update app

**Solution**:
- Try uninstall and reinstall
- Check version number is valid
- Verify internet connection
- View logs for specific error
- Report to app author

### Icon Not Displaying

**Symptom**: App card shows default icon instead of custom icon

**Solution**:
- Refresh page
- Clear browser cache
- Check if icon URL is valid
- Try reinstalling app
- Report to app author

### Publish Rejected

**Symptom**: Cannot publish app to Store

**Solution**:
- Check if logged in
- Verify all required fields are filled
- Check version number (must be > old version)
- Ensure icon is uploaded
- Check internet connection
- View specific error message

---

## 🎯 Roadmap Features

Upcoming features:

- ⏳ **Ratings & Reviews**: Rate and review apps
- ⏳ **Comments**: Comment and discuss
- ⏳ **Favorites**: Mark favorite apps
- ⏳ **Collections**: Create app collections
- ⏳ **Advanced Search**: Advanced search with filters
- ⏳ **Author Profiles**: Author profile pages
- ⏳ **Analytics**: Statistics for authors
- ⏳ **Monetization**: Support for paid apps (optional)

---

## 📞 Support

### Reporting Issues

If you encounter issues with:

- **App Store platform**: Create issue on GitHub
- **Specific app**: Contact app author
- **Installation/Update**: See [Troubleshooting](../troubleshooting/common-issues.md)

### Contributing

You can contribute by:

- 📝 Publishing quality apps
- ⭐ Rating and reviewing apps (coming soon)
- 🐛 Reporting bugs
- 💡 Suggesting new features
- 📖 Improving documentation

---

## 🔗 Related Links

- [App Builder Guide](app-builder-guide.en.md) - Guide to creating apps
- [Getting Started](getting-started.md) - Getting started with Komfy Studio
- [Models Management](models-management.md) - Managing models
- [Troubleshooting](../troubleshooting/common-issues.md) - Troubleshooting

---

**Last Updated**: 2026-02-06  
**Version**: 1.0.0
