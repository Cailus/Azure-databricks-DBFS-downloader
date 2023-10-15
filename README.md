# Azure-databricks-DBFS-downloader
Download DBFS data quickly on adb envs

# NOT UPDATED IN A YEAR

# @Description
Much faster way to download Data files from adb envs: you just click a 'download button'

# @summary
1. HOW TO ADD THE FUNCTION TO YOUR BROWSER
2. HOW TO USE THE DOWNLOAD FUNCTION
3. Q/A
4. TROUBLESHOOTING

----------------------------------------
----------------------------------------


# HOW TO ADD THE FUNCTION TO YOUR BROWSER:

(only works with adb) (should work for any env)

1. open a new tab (Ctrl T) on your browser
2. go to your bookmarks configuration and set it to "always show" (so you will be able to see your favorites toolbar below the url
3. go to google.com
4. Save as a favorite
5. edit your google.com bookmark URL
6. change the URL (google.com) to the following code (make sure it is 100% identical to the code below):

javascript:(function(){window.open("https://"+window.location.href.split("/")[2]+"/files/"+(document.querySelector("div.dbfs-openpath > input").value).substr(11)+"/"+document.querySelector("#sidebar > div > div.sidebar-alt > div:nth-child(1) > div > div.data-panel-body > div > div.filetree-container > div > div > nav:nth-child("+(document.querySelector("div.dbfs-openpath > input").value).split("/").length+") > ul > li.filetree-list-item.has-menu.selected > a > span").innerText,"_blank");})();

7. Add a name to your favorite (example: "adb download")
8. click ok


----------------------------------------
----------------------------------------


# HOW TO USE THE DOWNLOAD FUNCTION:

Inside any adb env:

1. Open Data
2. Open a directory
3. Click on a file name (example: something.csv)
4. click on your download bookmark.


----------------------------------------
----------------------------------------


# Function Q/A (troubleshooting in next section)

Q. Is this code dangerous somehow?

A. No. The code does exactly the same process done manually, but automatically.


Q. Will the code work in all envs and in any directories?

A. Unknown at the moment. It worked in all envs and directories tested.


Q. Does it work with all file extensions?

A. It should.


Q. What about a "download directory" function?

A. I created it, worked, and somehow forgot to push here and lost the code. The logic is pretty much the same: just add a loop, etc. Feel free to add a PR.

Q. Is the code future proof?

A. Maybe. If microsoft changes ADB considerably, all paths might change, which means that the program won't work anymore.


Q. Fixing the function will be difficult if the function doesn't work anymore?

A. No. Just changing the path parameter inside document.querySelector() will fix it.


Q. Will it work with any browsers?

A. Confirmed: google chrome, firefox, edge, safari.


----------------------------------------
----------------------------------------


# Troubleshooting


Q. Doesn't work.

is the code in the URL identical to the one above?
if yes: continue
if no: make sure the code is identical.
how? Open your download bookmark with a right click, click on edit, and compare the URL to the code above.


Q. Is the bookmarks tab showing below the URL?

if yes: continue
if no: make sure it is showing below the URL.

Q. Are you changing tabs before clicking download?

if yes: don't change tabs before clicking download
if no: continue

Q. Are you selecting the file (is it greyed out in adb) before clicking on "download"?

if yes: continua
if no: select the file before clicking download

If you reached this part and the function still doesn't work, feel free to find a fix and send a PR.


----------------------------------------
----------------------------------------
