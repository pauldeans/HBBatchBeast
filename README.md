# HBBatchBeast (Windows, macOS and Linux)

A simple GUI application for Handbrake on Windows with an emphasis on batch conversion (including recursive folder scans and folder watching). The destination folder structure is kept the same as the source folder structure. Media in subfolders is also converted. Multiple folders can be monitored and different conversion presets can be specified for each folder. There is also a health check feature which can scan for corrupt video files using Handbrakes's '--scan' feature, although this
is not always accurate.

This is a standalone program on Windows but requires Handbrake to be installed on Linux and Mac. 

![Screenshot](https://i.imgur.com/MVS7yTb.png)

Demo video -https://sendvid.com/x9q0mzm1

-------------------------------------------------------------
INSTALLATION - Windows:

Step 1:Download hbbatchbeast-Windows.7z from the release page and extract  it:

https://github.com/HaveAGitGat/HBBatchBeast/releases

Step 2:Run HBBatchBeast.exe

Settings help:https://github.com/HaveAGitGat/HBBatchBeast/blob/master/Settings%20help

-----------------------------------------------------------------------------


INSTALLATION - macOS:

Step 1: Make sure you have HandbrakeCLI installed. The easiest way is using Hombrew,
paste the following into a terminal:

/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew install handbrake


Step 2:Download hbbatchbeast-Mac.dmg from the release page:

https://github.com/HaveAGitGat/HBBatchBeast/releases

Step 3:Install the package

Step 4:Run hbbatchbeast from Launchpad


Settings help:https://github.com/HaveAGitGat/HBBatchBeast/blob/master/Settings%20help

-----------------------------------------------------------------------------

INSTALLATION - Linux:

Step 1: Make sure you have HandbrakeCLI installed - paste the following into a terminal:

sudo add-apt-repository ppa:stebbins/handbrake-releases

sudo apt-get update

sudo apt-get install handbrake-cli handbrake-gtk



Step 2:Download hbbatchbeast-Linux.deb from the release page:

https://github.com/HaveAGitGat/HBBatchBeast/releases

Step 3:Install the package

Step 4:Run hbbatchbeast 

Settings help:https://github.com/HaveAGitGat/HBBatchBeast/blob/master/Settings%20help

-------------------------------------------------------------


The program scans the source folder for all files. It then compares the source folder files with the destination folder files to see if any of the source files exist in the destination folder already. If not, the program queues the files for conversion.
 
The 4 worker modules then work through the conversion queue. If periodic scanning is enabled then the program will run at the chosen interval.

After it a bit more testing it seems that weird things can happen if you monitor a folder which is being downloaded to. It seems sometimes conversions start before a file has fully downloaded. To solve this, I recommend using a temporary download folder before moving completed files into your HBBB source folder.

If you use a download program which has an 'incomplete downloads' folder etc, do not put that folder inside your main source folder else you may end up converting each file twice.

The program won't work properly if you put the destination folder in a folder inside the source folder because the program is recreating the source folder structure inside the destination folder structure. It will cause an infinite loop of creating more and more sub-folders each time you run the program. So it will NOT work properly if you do this:

Source:

D:\Videos

Destination:

D:\Videos\Converted

It will work properly if you do this etc:

Source:

D:\Videos

Destination:

D:\Converted
