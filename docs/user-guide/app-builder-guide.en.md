# 🛠️ App Builder User Guide

**App Builder** is a powerful tool that allows you to create custom AI applications from your own ComfyUI workflows, with an intuitive and easy-to-use interface.

---

## 📋 Table of Contents

- [Introduction](#introduction)
- [Quick Start](#quick-start)
- [5-Step Process](#5-step-process)
  - [Step 1: Upload Workflow](#step-1-upload-workflow)
  - [Step 2: App Information](#step-2-app-information)
  - [Step 3: Check Dependencies](#step-3-check-dependencies)
  - [Step 4: Design Interface](#step-4-design-interface)
  - [Step 5: Preview & Deploy](#step-5-preview--deploy)
- [App Management](#app-management)
- [Publishing to App Store](#publishing-to-app-store)
- [Tips & Best Practices](#tips--best-practices)
- [Troubleshooting](#troubleshooting)

---

## 🎯 Introduction

App Builder allows you to:

- ✅ **Create custom AI applications** from ComfyUI workflows
- ✅ **Design interfaces** with drag-and-drop builder
- ✅ **Auto-detect dependencies** (models, custom nodes)
- ✅ **Test directly** during development
- ✅ **Store offline** and use immediately
- ✅ **Publish to App Store** to share with the community

---

## 🚀 Quick Start

### Accessing App Builder

1. Open **Komfy Studio**
2. Click on the **"Apps"** tab in the left sidebar
3. Click the **"Builder"** button in the top right corner
4. Or click **"Create New App"** from My Apps dashboard

### Requirements

- ✅ A tested and working ComfyUI workflow (`.json` file)
- ✅ Backend running and connected successfully
- ✅ Required models and custom nodes installed

---

## 📝 5-Step Process

### Step 1: Upload Workflow

**Purpose**: Import your ComfyUI workflow into App Builder

#### How to:

1. **Choose workflow source**:
   - **Upload File**: Click "Upload Workflow File" and select `.json` file
   - **From Library**: Select from saved workflows list

2. **Confirm workflow**:
   - System will automatically analyze the workflow
   - Check nodes and parameters
   - Detect customizable inputs

3. **Click "Next"** to continue

#### 💡 Tips:

- Ensure workflow is thoroughly tested in ComfyUI before importing
- Workflow should have clear structure with easily adjustable parameters
- Avoid overly complex workflows with many logic branches

---

### Step 2: App Information

**Purpose**: Provide metadata and descriptive information for the application

#### Information Fields:

##### 📌 Basic Information

- **App Name** (required):
  - Display name of the application
  - Should be short and memorable (e.g., "Portrait Generator", "Style Transfer AI")
  
- **Description** (required):
  - Detailed description of app functionality
  - Explain input/output
  - Suggest optimal usage

- **Icon** (recommended):
  - Click "Upload Icon" to select image
  - Format: PNG, JPG, WebP
  - Recommended size: 512x512px
  - Icon will be automatically resized and optimized

##### 🏷️ Classification

- **Category**:
  - Image: Image creation/editing apps
  - Video: Video creation/editing apps
  - Audio: Audio processing apps
  - General: Other applications

- **Tags** (optional):
  - Add keywords for easy searching
  - E.g., "portrait", "anime", "realistic", "fast"

##### 📦 Technical Information

- **Version**:
  - Follow Semantic Versioning standard (e.g., 1.0.0)
  - Increment version when updating app

- **Author**:
  - Author name (automatically retrieved from login info)

#### 💡 Tips:

- Write clear, easy-to-understand descriptions
- Choose beautiful and function-related icons
- Use appropriate tags to increase discoverability

---

### Step 3: Check Dependencies

**Purpose**: Verify required models and custom nodes

#### Automatic System:

App Builder will automatically:
- ✅ Analyze workflow and detect dependencies
- ✅ Check installed models
- ✅ Check installed custom nodes
- ✅ Display missing items (if any)

#### Dependency Status:

- **✅ Installed**: Already installed, ready to use
- **⚠️ Missing**: Not installed, needs download
- **ℹ️ Optional**: Not required, can be skipped

#### Handling Missing Dependencies:

1. **Missing models**:
   - Click "Download" to download model
   - Or go to **Tools > Models Manager** to install manually

2. **Missing custom nodes**:
   - Click "Install" to install node
   - Or go to **Tools > Custom Nodes** to install manually

3. **After installation**:
   - Click "Revalidate" to recheck
   - Ensure all dependencies are ✅ before continuing

#### 💡 Tips:

- Install all dependencies before publishing
- Clearly note requirements in app description
- Test thoroughly with different models if app supports multiple models

---

### Step 4: Design Interface

**Purpose**: Create an intuitive user interface for the application

#### 🎨 Design Canvas

This step allows you to design the app layout with a drag-and-drop interface.

##### UI Components:

###### 📝 Input Controls

- **Text Input**:
  - Enter text prompts, descriptions
  - Supports multiline, placeholder
  - Bind to node parameters

- **Number Input**:
  - Enter numbers (steps, CFG, seed, etc.)
  - Supports min/max, step increment
  - Slider or input box

- **Dropdown/Select**:
  - Choose from list (models, samplers, schedulers)
  - Single or multi-select

- **Checkbox/Toggle**:
  - Enable/disable features
  - Boolean parameters

- **Image Upload**:
  - Upload input images
  - Preview thumbnail
  - Drag & drop support

###### 🎛️ Advanced Controls

- **Slider**:
  - Adjust continuous values
  - Visual feedback

- **Color Picker**:
  - Select colors
  - Hex/RGB output

- **File Upload**:
  - Upload other files (video, audio, etc.)

###### 📊 Display Components

- **Label/Text**:
  - Display static text
  - Instructions, notes

- **Divider**:
  - Separate sections
  - Organize layout

- **Group/Container**:
  - Group controls together
  - Collapsible sections

##### 🔗 Parameter Binding

**Link UI controls to workflow parameters**:

1. **Select component** on canvas
2. **Open Properties Panel** on the right
3. **Select "Bind to Parameter"**
4. **Choose node and parameter** from workflow
5. **Configure mapping** (if transform needed)

**Example**:
```
Text Input "Prompt" → KSampler.positive
Number Input "Steps" → KSampler.steps
Dropdown "Model" → CheckpointLoaderSimple.ckpt_name
```

##### 🎯 Layout Organization

- **Drag & Drop**: Drag components onto canvas
- **Resize**: Adjust component sizes
- **Reorder**: Arrange display order
- **Group**: Group related controls
- **Responsive**: Layout auto-adjusts to screen size

#### 💡 Tips:

- Arrange controls in logical order (prompt → settings → advanced)
- Group related parameters into sections
- Use labels and tooltips to guide users
- Test layout on different screen sizes
- Hide advanced parameters in collapsible sections

---

### Step 5: Preview & Deploy

**Purpose**: Test the application and save to library

#### 🎬 Preview & Test

##### Test Interface:

This step displays the app in a real environment:

- **Left Panel**: Form with controls you designed
- **Right Panel**: Preview generation results

##### Test Workflow:

1. **Fill in information** in the form (prompt, parameters)
2. **Click "Generate"** to test
3. **View results** in the right panel
4. **Check**:
   - ✅ All controls work correctly
   - ✅ Parameters are passed accurately
   - ✅ Output displays in correct format
   - ✅ No generation errors

##### Debug:

If errors occur:
- Check console logs
- Verify parameter bindings
- Test again with different values
- Return to Step 4 to adjust

#### 💾 Deploy App

When testing is successful:

1. **Click "Deploy App"** (green button)
2. **Confirm information**
3. **Wait for system to save**
4. **App will appear in "My Apps"**

#### 🌐 Publish to Store (Optional)

If you want to share with the community:

1. **Click "Publish to Store"** (blue button with 🌐 icon)
2. **Confirm**:
   - All information is complete
   - Icon uploaded
   - Dependencies fully listed
3. **Click "Confirm"**
4. **App will be packaged (.kapp) and uploaded to App Store**

#### 💡 Tips:

- Test thoroughly with various inputs
- Check edge cases (empty input, extreme values)
- Ensure error handling works well
- Write clear description before publishing

---

## 📱 App Management

### My Apps Dashboard

Access: **Apps > My Apps** or click **"My Apps"** in App Builder

#### Functions:

##### 📋 View List

- Display all created apps
- Information: Icon, name, category, version
- Status: Local, Published

##### ✏️ Edit

1. Click **Edit icon** (✏️) on app card
2. App Builder will open with saved data
3. Edit any step
4. Click **"Update App"** to save changes

##### 🗑️ Delete

1. Click **Delete icon** (🗑️)
2. Confirm deletion
3. ⚠️ **Warning**: Cannot recover after deletion

##### 📤 Export

1. Click **Export icon** (📤)
2. Choose save location for `.kapp` file
3. Use for:
   - Backup application
   - Share with others
   - Import to another machine

##### 🌐 Publish

1. Click **Publish icon** (🌐)
2. Review information
3. Confirm publish
4. App will appear on App Store

---

## 🏪 Publishing to App Store

### Publishing Process

#### 1️⃣ Preparation

Ensure your app:

- ✅ **Works stably**: Thoroughly tested, no errors
- ✅ **Complete information**: Name, description, icon, category
- ✅ **Clear dependencies**: Fully list required models and nodes
- ✅ **Detailed description**: Usage instructions, requirements
- ✅ **High-quality icon**: Beautiful, clear, relevant image

#### 2️⃣ Publish

**From App Builder** (Step 5):
- Click **"Publish to Store"**

**From My Apps**:
- Click **Publish icon** (🌐) on app card

#### 3️⃣ Confirmation

The system will:
1. Package app into `.kapp` file
2. Upload app and icon
3. Publish app to App Store

#### 4️⃣ After Publishing

- App appears on **App Store** immediately
- Other users can find, view, and install
- You can track installation count (coming soon)

### Updating Published Apps

When updates are needed:

1. **Edit app** from My Apps
2. **Increase version number** (e.g., 1.0.0 → 1.1.0)
3. **Modify** necessary content
4. **Update App**
5. **Publish again**

The system will:
- Check version (must be higher than old version)
- Create new version in database
- Users will see "Update Available" notification

### Rules & Best Practices

#### ✅ Do:

- Write clear, easy-to-understand descriptions
- Upload high-quality icons
- Fully list requirements
- Test thoroughly before publishing
- Update version following SemVer standard
- Respond to user feedback

#### ❌ Don't:

- Publish untested apps
- Provide incomplete information or poor descriptions
- Use unrelated icons
- Spam unnecessary versions
- Copy others' apps

---

## 💡 Tips & Best Practices

### Workflow Design

- **Simplify**: Simpler workflows are easier to maintain
- **Parameterize**: Expose important parameters
- **Default values**: Set reasonable default values
- **Error handling**: Handle edge cases in workflow

### UI Design

- **User-friendly**: Intuitive, easy-to-use interface
- **Logical flow**: Arrange controls in logical order
- **Visual hierarchy**: Clear grouping and information hierarchy
- **Responsive**: Test on multiple screen sizes

### Metadata

- **Descriptive names**: Short, memorable app names
- **Detailed description**: Clearly explain functionality and usage
- **Proper categorization**: Choose appropriate category and tags
- **Version control**: Manage versions following standards

### Testing

- **Comprehensive testing**: Test with various inputs
- **Edge cases**: Check special cases
- **Performance**: Ensure app runs smoothly
- **User feedback**: Listen and improve based on feedback

---

## 🔧 Troubleshooting

### Workflow Upload Error

**Symptom**: Cannot upload workflow file

**Solution**:
- Check if file is in `.json` format
- Open file with text editor, verify valid JSON
- Try exporting workflow from ComfyUI again
- Check file size (not too large)

### Dependencies Not Detected

**Symptom**: System doesn't display all required models/nodes

**Solution**:
- Ensure backend is running and connected
- Refresh models/nodes list in Tools
- Check if workflow uses non-standard custom nodes
- Try revalidating dependencies

### UI Controls Cannot Bind

**Symptom**: Cannot link control to parameter

**Solution**:
- Check if workflow has corresponding node
- Verify parameter name is correct
- Try deleting and recreating control
- Check if data types match (string, number, etc.)

### Test Generation Error

**Symptom**: Error when clicking "Generate" in Preview

**Solution**:
- Check console logs for specific error
- Verify all required parameters are bound
- Test workflow directly in ComfyUI
- Check backend logs
- Verify models loaded correctly

### Publish Failed

**Symptom**: Cannot publish app to Store

**Solution**:
- Check internet connection
- Verify logged in
- Verify all required fields filled
- Check version number (must be > old version if updating)
- Try again after a few minutes

### App Not Appearing in My Apps

**Symptom**: After deploying, app doesn't display

**Solution**:
- Refresh page (Ctrl+R)
- Check "My Apps" tab is selected
- Check console logs for errors
- Try creating app again
- Check database connection

---

## 📞 Support

If you encounter issues not listed above:

1. Check [Common Issues](../troubleshooting/common-issues.md)
2. See [FAQ](../troubleshooting/faq.md)
3. Create issue on GitHub
4. Contact support team

---

**Last Updated**: 2026-02-06  
**Version**: 1.0.0
