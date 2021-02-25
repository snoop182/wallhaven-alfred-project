# wallhaven-alfred-project

!!Disclaimer!!!

- I'm not a programmer, and I'm a beginner. 
- English is not my main language, so be patient pls or step back.
- I created this project just for myself, and decided to share it with you If you think that my code is shit, that's true lol. Some constructive criticism welcome

!!!Disclaimer!!!


- Primary language - php
- Alfred use Wallhaven API v1

Main features :
- MacOS Wallpaper change by hotkey/item in list filter or cron (with chosen interval)
- Single & dual display support
- Multiple spaces support
- Each space will have a unique Wallpaper


Requirements :

- MacOS and Alfred 4 with power pack
- « Displays have separate Spaces » checked, see https://i.imgur.com/5EVjDWA.png
- Account on Wallhaven https://wallhaven.cc/
- Wallhaven collections with wallpapers
------------------------------------------------------------------------------------------------------------------

My dictionary :
- Local collection - collection that was collected(lol) by Alfred and stored in local data base in your temporary folder
- Wallhaven collection - collection on Wallhaven project kappa
- Cron - part of Alfred workflow that change Wallpaper automatically with the interval
- Cronjob - event of automatic Wallpaper changing
- Local db - data base, stored in temporary folder that Alfred use

Other Features :
- Alfred will create a local data base (db, type sqlite) in your temporairy folder (var:tmppath)
- Alfred will collect & store information about your Wallhaven collections and images in local db
- Alfred can set up images from default local collection or from the choosen one, to all Mac OS spaces at once (each space have unique wallpaper)
- Alfred don't download all images from the collection.
- Alfred can reset desktoppicture.db (MacOS db for the wallpapers)
- Alfred can delete tmp folder
- Alfred can set up a cronjob for changing wallpapers from default local collection or random source (automatic change with interval)
- Update local collections without ddos Wallhaven
- WILL work on single & dual displays env
- Manual random wallpaper install from wallhaven
- Cron random wallpaper install from wallhaven
- Wallpaper random change without repeat
- Check list of downloaded images
- Reset downloaded image/all images in local db for re-use in future (in case if you very like specifiic wallpaper)
- Get Wallhaven direct link for downloaded image
- Cron ON -> activate the cronjob
- Cron OFF -> deactivate the cronjob
- Change cron interval
- NFSW wallpapers with your API key
- Dynamic purity select
- Wallpaper random select by selected purity
- Check if VLC is runing in fullscreen or Safari/Chrome in fullscreen, if true stop automatic wellpaper change / I did this for not run "killall Dock" (restart the Dock) because if Dock will restarted even if you watch YT on fullscreen the dock will appear on your screen lol


Default data structure and variables :

--> tmppath

Directory where Alfred will store all images & local.db & script for cronjob
Ex : /Users/<!!!MACUSER!!!>/wallhaven
Where <!!!MACUSER!!!!> is you account name for macOS

--> apikey
Users are able to grant API access to some of their settings via an API key provided via their account settings here https://wallhaven.cc/settings/account

--> collectionID
ID of default collection, can be found at the end of the url of the collection page ex : https://prnt.sc/u8j7bo

--> croncollectionID
ID of the collection for cronjob (timer)

--> cronjobpath
Path to the cronjob (Agent) by default in Mac OS : ~/Library/LaunchAgents

----> numscreens default 1 but you can put 2 if yu have 2 screens env 
Alfred will change automaticaly - don't tuch it after
WARNING!!! I didn't tested it on 3 screens env, so i think it will not work correctly
!!!WARNING2!!! Don't setup 0. Just 1 or 2!!!!!!

----> lastcronexec
Las time when cronjob was executed by mac os. For the first time use 0, Alfred will update this variable when he need it


---> resolution
Resolution of your screen ex 2560x1600

----> dbpath
Path to the Mac OS data base for wallpapers. By deafault it's here : "/Users/<!!!MACUSER!!!!>/Library/Application Support/Dock/desktoppicture.db"
Where <!!!MACUSER!!!!> is you account name for Mac

---> cronstate
Source of cronjob, it ONLY CAN BE : "collection" OR "random"

---> purity
This is purity of wallpapers for Alfred.
By default you can set "all"
Alfred can change this for you in "rating".
To grain acces to "rating" tap "rating" in alfred or select rating in "Main Enter_point" (tap wal in Alfred and see the magic)


[[[!!!!!READ THIS BEFORE START USING!!!!]]]]
1. Set the main Environment Variables
- apikey
- collectionID
- croncollectionID
- cronstate
- currentdbstate, put 0
- dbpath
- lascronexec, put 0
- numscreen, put 1 or 2 if you have 2 displays
- purity, put "all"
- resolution, put your resolution, in strict format. ex : 2560x1600
- tmppath, put any path (you may even don't create the directory). ex : Ex : /Users/<!!!MACUSER!!!>/wallhaven
- username, put your username that you use on Wallhaven site.

2. Tap "wal" in Alfred and select first install
3. chose collection
4. wait

-------------------> Enjoy

Cron first run
1. Tap « cr » in Alfred
2. Run « First cron install »

-------------------> Enjoy

P.S. Don't tuch bandleID pls
