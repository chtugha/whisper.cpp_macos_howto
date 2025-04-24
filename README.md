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
Open Terminal
<BR>
<BR>
![Terminal](https://github.com/user-attachments/assets/12c5ef67-59a8-4d8d-adcf-d25e0780449a)
<BR>
<BR>
Install Xcode command line tools by typing following command:
<BR>
<BR>
_`xcode-select --install`_
<BR>
<BR>
Leave the terminal window open
<BR>
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
switch to terminal and type:
<BR>
<BR>
_`echo 'eval $(/opt/homebrew/bin/brew shellenv)' >> $HOME/.zprofile`_  (This would be different on intel macs)
<BR>
<BR>
Exit the shell:
<BR>
<BR>
_`exit`_
<BR>
<BR>
Close terminal
<BR>
<BR>
<BR>
**3.) Install all necessary things**
<BR>
<BR>
Open Terminal again and enter the following command:
<BR>
<BR>
_`brew install git cmake wget ninja miniconda ffmpeg libomp llvm`_
<BR>
<BR>
If one of the programs that are being installed is asking for something - just always hit the `Enter` key or type _`yes`_ or _`agree`_ or whatever necessary for the default option
<BR>
<BR>
Find out which version of libomp you installed:
<BR>
<BR>
_`ls /opt/homebrew/Cellar/libomp`_
<BR>
<BR>
Add the variables for the compiler. Replace the xes with your version number.
<BR>
<BR>
_`export CC="/opt/homebrew/Cellar/llvm/`_**XX.X.X**_`/bin/clang"`_
<BR>
_`export CXX="/opt/homebrew/Cellar/llvm/`_**XX.X.X**_`/bin/clang++"`_
<BR>
_`export LDFLAGS="-L/opt/homebrew/Cellar/llvm/`_**XX.X.X**_`/lib"`_
<BR>
_`export CPPFLAGS="-I/opt/homebrew/Cellar/llvm/`_**XX.X.X**_`/include"`_
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
Enter the new Directory:
<BR>
<BR>
_`cd whisper.cpp`_
<BR>
<BR>
<BR>
**5.) compile whisper**
<BR>
<BR>
Type into terminal:
<BR>
<BR>
_`cmake -G Ninja -B build -DCMAKE_BUILD_TYPE=Release -DWHISPER_CCACHE=OFF`_
<BR>
<BR>
