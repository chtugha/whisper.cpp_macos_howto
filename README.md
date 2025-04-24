# whisper.cpp_macos_howto
**How to install a whisper instance locally on an Apple silicon machine from scratch**
<BR>
<BR>
<BR>
**1.) Install Xcode from the App Store:**
<BR>
<BR>
![Xcode](https://github.com/user-attachments/assets/72314b18-4e6c-474a-9661-d6c08e1dc94b)
<BR>
<BR>
Open the app to agree to the license agreement and install the version for your computer. You don't need the code completion thing.
<BR>
<BR>
Close Xcode afterwards.
<BR>
<BR>
**2.) Download the latest version of the homebrew installer:**
<BR>
<BR>
Klick here https://github.com/Homebrew/brew/releases/
<BR>
<BR>
Klick on the latest release to download it (Homebrew-4.4.32.pkg in this example)
<BR>
<BR>
![Homebrew](https://github.com/user-attachments/assets/e6d50eef-5cbe-4199-b9fc-cd37a0e80ebb)
<BR>
Install the homebrew package you downloaded
<BR>
<BR>
<BR>
<BR>
**3.) Install all necessary things**
<BR>
<BR>
Open Terminal
<BR>
<BR>
![Terminal](https://github.com/user-attachments/assets/12c5ef67-59a8-4d8d-adcf-d25e0780449a)
<BR>
<BR>
and enter following command:
<BR>
<BR>
_`brew install git cmake wget ninja miniconda ffmpeg`_
<BR>
<BR>
If one of the programs that are being installed is asking for something - just always hit the `Enter` key or type _`yes`_ or _`agree`_ or whatever necessary for the default option
<BR>
<BR>
<BR>
**4.) Activate Miniconda**
<BR>
<BR>
Enter following command into terminal:
<BR>
<BR>
_`conda init --all`_
<BR>
<BR>
Close Terminal after the initialization
<BR>
<BR>
<BR>
**5.) Download whisper.cpp from github**
<BR>
<BR>
Open Terminal again. You should see this: `( base )` as leading information of your shell. It means that you successfully installed miniconda.
<BR>
<BR>
![shell](https://github.com/user-attachments/assets/7f60204b-013f-424c-8f80-c6a491075e94)
<BR>
<BR>
Create a new folder for whisper:
<BR>
<BR>
_`mkdir Whisper`_
<BR>
<BR>
Enter the folder:
<BR>
<BR>
_`cd Whisper`_
<BR>
<BR>
Download the latest whisper release from github:
<BR>
<BR>
_`git clone https://github.com/ggml-org/whisper.cpp.git`_
<BR>
<BR>
Enter the new 
