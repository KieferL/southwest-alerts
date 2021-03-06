# Details

This is an application that can be used to monitor booked southwest flights for
price changes. It logs into the accounts credentials are proided for, and
checks to see if rebooking the flight would result in a lower price. If a lower
price is available it will email you via the Mailgun api. It will not
automatically rebook the flight for you.

This script runs off of Python and Mailgun. Mailgun simply creates a Domain that this script can "speak" to, and send you emails if a lower price is found. Pretty boring, but mildly neat.

The original script and instructions were based on a Linux system, and created by /u/ninja_batman. His simple way to enable this program is through a method that requires a Virtual Machine to be run. In my scenario, I do not have enough hard drive space to run a VM. Regardless of the pain it was to understand Python with no background in it, I wanted to share my findings for /r/Churning to follow in case they are in a similar situation.

# Setup

## Create Accounts & Install Programs

1. Create Mailgun account (API Key & Domain)

Setup a [mailgun account](https://www.mailgun.com/), and create an [api
key](https://app.mailgun.com/app/account/security). I made a Notepad file with all the important links and directories- I suggest you do the same. Add the API Key to your Notepad file.

Use the default Mailgun Domain by clicking the "Domains" tab and copying the link. It should read something like "sandboxTONSOFRANDOMCHARACTERS.mailgun.org". Keep note of that Domain in your Notepad file, we will need this later.

2. Install Python (if not already installed)
   [windows](https://www.python.org/downloads/windows/)

As of now, the latest Python build is 3.6.3. Install your version and locate the directory that it has been installed to. For myself, that was simply "C:\Python34". Take note of that install directory in Notepad, we are going to need that later on. 

3. Change Your PATH

4. Install PIP for Python

PIP stands for "PIP Installs Packages", and it does exactly that in Python. Now that your PATH has been changed to the directory that Python was installed, we will take our first dive into it.
   Download PIP at ([windows](https://pip.pypa.io/en/stable/installing/)

# Running the Script

## Putting This All Together

1. Pull repository

```
git clone xur17/southwest-alerts
cd southwest-alerts
```
*****ADD CORRECT GITHUB LINK

2. Install dependencies

```
pip3 install -r requirements.txt
```

3. Set environment variables (replacing value with the appropriate value)

```
export MAILGUN_DOMAIN=VALUE
export MAILGUN_API_KEY=VALUE
export USERNAME1=VALUE
export PASSWORD1=VALUE
export EMAIL1=VALUE
```

*****EDIT PATH AGAIN

4. Run

***** "export PYTHONPATH=." This in it's most simple form allows Python to search in all of your directories, although we will be working out of the root folder for this script. This step drove me CRAZY because I kept receiving an error. This step many not be necesary for all, but if you receive an error similar to "ImportError: No module named 'southwestalerts'" you will need to do this step.


```
python southwestalerts/app.py
```
