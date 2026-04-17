# startrek2e
Startrek 2e plugin for LackeyCCG


HOWTO update

branch the repo branch playable

get new card data from [https://www.trekcc.org/lackey2020/](https://www.trekcc.org/lackey/2020.php)

replace the [sets/Virtual.txt](sets/Virtual.txt) and [sets/Physical.txt](sets/Physical.txt) with the new data.
place new images in sets/setimages/general/ as 357x499px jpg

update 
[changelog.txt](changelog.txt)

add new expansion to
[formats.txt](formats.txt)

set new date to yesterday and add replaced images
[uninstall.txt](uninstall.txt)

update the version number and add short changes
[version.txt](version.txt)

Set new date at the top of
[updatelist.txt](updatelist.txt)

generate new checksum 
```/mkupdate plugins/startrek2e/updatelist.txt```

make new PR
