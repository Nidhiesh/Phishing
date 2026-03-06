# ✅ WhatsApp Web Detection - Quick Setup Checklist

## Pre-Installation

- [ ] Chrome/Microsoft Edge browser installed
- [ ] Developer mode enabled in browser (chrome://extensions/)
- [ ] Python 3.7+ installed on system
- [ ] Flask and scikit-learn installed (`pip install flask flask-cors scikit-learn`)

## Installation Steps

### Backend Setup
- [ ] Navigate to `backend/` folder
- [ ] Run `python app.py`
- [ ] See message: `✓ Model loaded successfully`
- [ ] See message: `✓ Vectorizer loaded successfully`
- [ ] Backend running on `http://localhost:5000`
- [ ] Keep this terminal open while testing

### Extension Installation
- [ ] Open Chrome: `chrome://extensions/`
- [ ] Enable **Developer mode** (toggle in top right)
- [ ] Click **Load unpacked**
- [ ] Select the `extension` folder
- [ ] Extension icon appears in toolbar
- [ ] Version shows **3.1** in popup

## WhatsApp Web Setup
- [ ] Navigate to `https://web.whatsapp.com`
- [ ] Scan QR code with your phone
- [ ] Wait for chats to fully load (3-5 seconds)
- [ ] Extension icon shows green checkmark (✓)

## Quick Functionality Test

### Test 1: Scam Message Detection ✓
1. [ ] Open any WhatsApp chat
2. [ ] Send yourself: `"Verify your WhatsApp: bit.ly/verify123"`
3. [ ] Look for **RED badge** with "⚠️ SCAM"
4. [ ] **Pop-up alert** appears after 1-2 seconds
5. [ ] Alert shows confidence score > 70%
6. [ ] Alert shows threat: "Suspicious shortener URL"

### Test 2: Suspicious Message Detection ✓
1. [ ] Send: `"Click here immediately to update account"`
2. [ ] Look for **ORANGE badge** with "⚠️ SUSPICIOUS"
3. [ ] Alert appears with orange header
4. [ ] Confidence score 25-70%

### Test 3: Safe Message ✓
1. [ ] Send: `"Hi, how are you?"`
2. [ ] **No badge** appears
3. [ ] **No alert** pops up
4. [ ] Message appears normal

### Test 4: Backend Offline Mode ✓
1. [ ] Close backend terminal (Ctrl+C)
2. [ ] Check popup - shows "Backend: Offline"
3. [ ] Send scam message
4. [ ] Still detects as SCAM using fallback
5. [ ] Restart backend: `python app.py`

## Verification Steps

### Browser Console Check (F12)
1. [ ] Press `F12` to open DevTools
2. [ ] Go to **Console** tab
3. [ ] Look for these messages:
   - `🛡️ Cyber Shield Content Script loaded`
   - `✓ WhatsApp Web monitoring started`
   - `📱 Found X existing WhatsApp messages to scan`

### Extension Popup Check
1. [ ] Click extension icon
2. [ ] **Status**: Shows "Protection Active" (green)
3. [ ] **Backend**: Shows "Backend: Online" or "Backend: Offline"
4. [ ] **Toggle Detection**: Checkbox is checked ✓
5. [ ] **Platforms**: Shows "💬 WhatsApp Web" in list

### Message Analysis Logs
1. [ ] Open DevTools (F12 → Console)
2. [ ] Send a test message on WhatsApp
3. [ ] Look for: `[whatsapp] Found message: "..."`
4. [ ] If scam: `⚠️ [whatsapp] SCAM DETECTED:`

## Troubleshooting Checklist

### Messages Not Being Detected?
- [ ] Extension is actually loaded (icon visible in toolbar)
- [ ] Detection is enabled (toggle in popup)
- [ ] WhatsApp Web page is fully loaded (wait 5 seconds)
- [ ] Hard refresh page: `Ctrl+Shift+R`
- [ ] Check DevTools console for errors (F12)
- [ ] Try sending a test message to yourself

### Backend Shows "Offline"?
- [ ] `python app.py` is running in terminal
- [ ] Terminal shows `Running on http://localhost:5000`
- [ ] No firewall blocking port 5000
- [ ] `model.pkl` file exists in `backend/` folder
- [ ] `vectorizer.pkl` file exists in `backend/` folder
- [ ] If missing: Run `python train_model.py`

### Alerts Not Appearing?
- [ ] Notifications are enabled in popup
- [ ] Message text is > 3 characters
- [ ] Wait 1-2 seconds for alert to appear
- [ ] Check if alert appears at bottom-right corner
- [ ] Scroll page if alert is cut off

### Extension Not Loading?
- [ ] `chrome://extensions/` shows the extension listed
- [ ] Extension shows as "Enabled" (toggle is on)
- [ ] Manifest.json has valid JSON syntax
- [ ] No red error messages in DevTools

## Performance Verification

✓ **Detection Speed**: Should be < 100ms per message  
✓ **Memory Usage**: Should be < 20MB  
✓ **CPU Impact**: Minimal (should not make fan spin)  

## Final Checklist

- [ ] Extension installed and enabled
- [ ] Backend server running
- [ ] WhatsApp Web fully loaded
- [ ] Test messages flagged correctly
- [ ] Alerts pop up as expected
- [ ] Backend status shows as "Online"
- [ ] No errors in DevTools console
- [ ] All 3 test cases pass

---

## 🚀 You're Ready!

If all checkboxes above are checked ✓, your **WhatsApp Web scam detection is fully operational**!

### Next Steps:
1. Monitor real conversations
2. Trust the alerts
3. Mark false positives to improve model
4. Share feedback for improvements

### Emergency Troubleshooting:
1. Check DevTools console (F12)
2. Restart browser extension (disable/enable)
3. Restart backend (`python app.py`)
4. Clear browser cache (Ctrl+Shift+Delete)
5. Reload WhatsApp Web (F5)

**Need Help?**  
- Review `EXTENSION_SETUP_GUIDE.md` for detailed instructions
- Check `WHATSAPP_DETECTION_GUIDE.md` for usage tips
- Review `CODE_CHANGES_SUMMARY.md` for technical details

---

**Status**: ✅ Ready for Production  
**Version**: 3.1  
**Last Updated**: March 2024
