# pptshots
Finding sensitive information in the trimmed parts of cropped images 


Cropping pictures inserted in a powerpoint presentation enables users to hide parts of a picture that they do not want to display. The problem is that Office’s cropping tool only modifies how the cropped image is displayed in the body of the document. The original picture remains intact. Cropped portions of the image are not completely removed from the document and can be seen by others if the file is uploaded to the internet. Data leakage can occur if there is sensitive data in the trimmed areas.

PPTSHOTS searches google for presentations by query, downloads them and checks for images where cropping has occured.

This solution uses goog.io, They have free and commercial packages available. Enter your key in the .env file

It is advised that you run the notebook in a sandbox or vm as it does involve downloading untrusted documents from the internet.


Clone the repository

`git clone https://github.com/dfaram7/pptshots.git`


Install the requirements

`pip install -r requirements.txt`

Run the notebook!

`jupyter notebook`

If you dont want to read all the code you can just SHIFT+ENTER down to th eexclamation marks and enter your search term

## Notes

It is actually pretty rare to find anything interesting, after several days only one presentation contained 'sensitive' information. In this instance an "unnamed US federal government executive branch organization" had unintentionally left some PII in a Facebook screenshot. I reported this to them and the presentation is no longer publicly facing.

Other less sensitive information included browser tabs and OS information from the screen peripheries which could be of minor value to an attacker but nothing too exciting. Interestingly, on a few occasions where screenshots had been taken with dual monitors there was an entire extra screen to examine - I didn't identify anything more valuable than a half filled in timesheet but there is potential for sizeable data to have been exposed if a spreadsheet or similar had been open.


