# One Million Arab Coders (OMAC) 
 
## Project: Downloading Videos Direct from YouTube 
 
## Mohamed Ahmed Makki

#### This project allows us to download any video from YouTube site,
#### first will prompt us to enter the link of the required video on the YouTube (full web address)
#### then the code will allow us to download the video with all necessary corresponding information such as:
#### Title of the video, Time-Length (Duration), Counts of Views, Brief Description and Ratings.


```python
# importing the required modules from libraries
from pytube import YouTube
import datetime
```


```python
# entering the desired Youtube Video link to be downloaded
url = input("Input The Youtube Video URL Address: ")
tube = YouTube(url)
```

    Input The Youtube Video URL Address: https://www.youtube.com/watch?v=TENU9b9RZCU
    


```python
# converting the duration of video from seconds to hour:minutes:seconds Format.

n=tube.length  
def convert(n):
    return str(datetime.timedelta(seconds = n))
```


```python
# printing all necessary information about the downloaded video.

# print the title of the downloaded video.
print("Full Title  :", tube.title)

# print the Duration of the downloaded video.
print("Duration    :", str(datetime.timedelta(seconds = n)))

# print the number of views for this Video.
print("Views       :", tube.views)

# print the first line of the Description
print("Description :", tube.description[:45])

# print the Ratings for the Video
print("Ratings     :", tube.rating)

 
```

    Full Title  : BEST PAVILIONS AT DUBAI EXPO 2020 (Top 30)
    Duration    : 0:30:22
    Views       : 114080
    Description : Video exploring around , United Arab Emirates
    Ratings     : 4.6622515
    


```python
# start the downloading process to the specific folder in the computer.

stream = tube.streams.get_highest_resolution()
stream.download('C:\\Users\mak\Downloads')

# print a download-completion note
print("Done!! . . . Fun Watching")
```

    Done!! . . . Fun Watching
    

### Notes:

####    - This program's default folder for downloading videos is (C:\\Users\user_name)
####      if you use the stream.download( ) code with empty parentheses, 
####      however, you may choose any other folder to download the video to, I chose the downloads folder 
####      'C:\\Users\mak\Downloads').
####    - Because the Description item (sometimes) contains a lot of information, the code here only allows one line for it. 
####      for a very brief description; it can be set to the default setting (by coding), which displays all full information for
####      the Description Item.
####    - The purpose of importing the datetime modules is to convert the (meaningless) huge time duration in seconds 
####      to a comprehensible format of hours:minutes:seconds


### Development: 

###    - This program could be developed into a standalone website tool that allows
###       users to download YouTube videos by merely inputting the video url link. 

###    - It can also be developed to download videos from other websites; besides 
###      downloading files in various formats such as txt, pdf, and photos with
###      different file extensions.
 


```python

```
