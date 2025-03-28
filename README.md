# 🔐 WELCOME CLASSICALMUSICHUBBS FINEST YOU HAVE MADE IT THIS FAR 🔐

## 🎮 Welcome, Code Breakers! 🎮

Congratulations on making it this far! YOUR challenge requires you to run a Python script that will generate a QR code leading to the last clue.

> **DON'T WORRY!** Even if you've never coded before, you can do this! Just follow these steps exactly as written.

---

## 📋 QUICK OVERVIEW
1. Install Python (a programming language)
2. Check that Python works
3. Install two helper tools
4. Create a simple script file
5. Run the script
6. Scan the QR code it creates
7. Find the final password!

---

## 🔧 Step 1: Install Python

### For Windows:
1. Download Python 3.9+ from [python.org](https://www.python.org/downloads/)
2. Run the installer
3. **SUPER IMPORTANT**: Check the box that says "Add Python to PATH" during installation ✅
   - This is easy to miss but will cause problems if you forget it!
4. Click "Install Now"

### For Mac:
1. Open Terminal (find it in Applications > Utilities, or search for "Terminal" in Spotlight)
2. Install Homebrew (it's like an app store for coding tools):
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
3. Install Python:
```
brew install python
```

### For Linux:
1. Python is likely already installed. If not:
```
sudo apt update
sudo apt install python3 python3-pip
```

---

## ✅ Step 2: Check If Python Installed Correctly

1. Open a terminal/command prompt:
   - **Windows**: Press Windows key, type "cmd" and press Enter
   - **Mac**: Open Applications folder > Utilities > Terminal
   - **Linux**: Press Ctrl+Alt+T

2. Type this command and press Enter:
```
python --version
```
(If that doesn't work, try `python3 --version`)

3. You should see something like "Python 3.9.5" (version may vary)
   - If you see this, great! Python is installed correctly
   - If you get an error, you might need to restart your computer and try again

---

## 📦 Step 3: Install Required Helper Tools

**💡 TIP: Copy-paste these commands to avoid typing errors!**

Run these commands in your terminal:
```
python3 -m pip install qrcode pillow
```

If you get any errors about pip not being found, try:
```
python3 -m ensurepip --upgrade
python3 -m pip install --upgrade pip
python3 -m pip install qrcode pillow
```

**Note for Mac users:** If you're still having issues, try this specific command:
```
/Library/Frameworks/Python.framework/Versions/3.13/bin/pip3 install qrcode pillow
```

---

## 📝 Step 4: Create The Python Script

### 💡 TIP: SAVE EVERYTHING TO YOUR DESKTOP FOR SIMPLICITY!

1. Open a simple text editor:
   - **Windows**: Notepad (search for it in the Start menu)
   - **Mac**: TextEdit (find in Applications)
   - **Linux**: Gedit or Nano

2. Copy the ENTIRE code block below:

```python
import qrcode
import base64

# The encrypted data that will be decoded and turned into a QR code
encrypted_data = "aHR0cHM6Ly9mbmFnenVua3NvYnlzZW9sZmFvaS5zdXBhYmFzZS5jby9zdG9yYWdlL3YxL29iamVjdC9wdWJsaWMvaW1hZ2UtaG9zdGluZy8vR3JvdXAlMjAxMTAucG5n"

# First we need to decode the data
def decode_data(data):
    # This function decodes base64 data
    decoded_bytes = base64.b64decode(data)
    return decoded_bytes.decode('utf-8')

# Now let's generate a QR code
def generate_qr_code(data):
    print("Generating QR code...")
    
    # Create qr code instance
    qr = qrcode.QRCode(
        version=1,
        error_correction=qrcode.constants.ERROR_CORRECT_H,
        box_size=10,
        border=4,
    )
    
    # Add data to the QR code
    qr.add_data(data)
    qr.make(fit=True)
    
    # Create an image from the QR Code
    img = qr.make_image(fill_color="black", back_color="white")
    
    # Save the image
    img.save("final_clue_qr.png")
    print("QR code generated! Open the file 'final_clue_qr.png' to scan it.")
    print("Scan the QR code with your phone to reveal the final password location.")
    print("\n*** IMPORTANT FINAL STEP ***")
    print("To complete the challenge, you must type in the main chat channel:")
    print("'yuja password: THE_PASSWORD'")
    print("Replace THE_PASSWORD with the actual password you find from the QR code.")
    print("Good luck!")

if __name__ == "__main__":
    print("Starting the final stage of the Cipher Challenge...")
    print("Decoding the secret data...")
    
    # Get the decoded URL
    decoded_url = decode_data(encrypted_data)
    
    # Generate QR code with the decoded URL
    generate_qr_code(decoded_url)
    
    print("Challenge complete! The QR code contains your final clue.")
```

3. Paste it into your text editor

4. Save the file:
   - Click "File" > "Save As"
   - **IMPORTANT**: Save it to your Desktop for easy access
   - Name it exactly: `generate_qr.py`
   - Make sure it saves as a `.py` file, not `.txt` or anything else
     - **Windows tip**: You might need to change "Save as type" to "All Files" and manually type `.py` at the end

---

## ▶️ Step 5: Run The Script

1. Go back to your terminal/command prompt
2. Now we need to navigate to your Desktop:

   - **Windows**: Type this and press Enter:
   ```
   cd Desktop
   ```

   - **Mac/Linux**: Type this and press Enter:
   ```
   cd ~/Desktop
   ```

   > 💡 **What is this `cd` thing?**: It stands for "change directory" - it's like double-clicking a folder to open it, but using text!

3. Run the script by typing:
```
python3 generate_qr.py
```

4. You should see messages about the script running and generating a QR code

---

## 🔍 Troubleshooting:

**Problem**: "No module named 'qrcode'" error
- **Solution**: Try installing again with: `python -m pip install qrcode pillow`

**Problem**: Can't find the cd command or Desktop
- **Solution**: 
  - **Windows**: Try `cd C:\Users\YourUsername\Desktop` (replace "YourUsername" with your actual username)
  - **Mac**: Try `cd /Users/YourUsername/Desktop`

**Problem**: Python command not found
- **Solution**: 
  - Try `python3` instead of `python`
  - Try restarting your computer

**Problem**: Nothing happens when you run the script
- **Solution**: Make sure you saved the file with the `.py` extension
- Are you in the right folder? Type `dir` (Windows) or `ls` (Mac/Linux) to see files in your current location

---

## 🎯 Step 6: Find The QR Code

1. Look on your Desktop for a new file called `final_clue_qr.png`
2. Double-click to open the image
3. Scan the QR code with your phone's camera app
4. The QR code will lead you to a URL with the final clue!

---

## 🏆 CONGRATULATIONS! 🏆

You've completed not just a cipher challenge but also your first programming task! The URL will reveal the next step. 

Good luck, and may the best code breaker win! 🎮🔐🎯
