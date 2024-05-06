<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# Personal Spotify album recommender

Building AI course project - Final project for the Building AI course.

## Summary

The aim of this project is to build a personal recommender for music albums on Spotify. My motivation for this project is that I'm a big music lover and I'm slightly dissatisfied with the recommendation currently offered by Spotify.

In my perception of music as such, the primary product had always been whole albums and not the songs by themselfs. I like to listen to whole albums, or some part of them if I don't have enough time to listen to the whole thing. The recommendation should by primarily based on the album cover which to some extent reflects the music itself.


## Background

I've noticed that most of my favorite albums have a similar style of cover art - the picture that is on the front of the CD, vinyl record, or as the artwork for the songs on that album on an online music platform. So I'd like to get recommendations of records I haven't heard that are similar in some way, based on covers of my favourite records. Furthermore, later I would of course include the music itself and its parameters in the recommendation system and the reason why I want to make recommendations based on images in the first phase is because I don't want to stay anchored in my favorite genres and gain more insight.

My goal is to get a few music albums recommended every day/week/month that I could immidiately play on Spotify.

## How do I expect it would be used?

1. First I need to get my favourite albums from Spotify and extract the images features
2. Get a list of as many music albums as I can get and extract the images features also from them
3. Make some random pick from albums that have similar album cover and that I have not heard yet


## Data sources and AI methods

* Get your favourite albums (including images) from the [Spotify API](https://developer.spotify.com/dashboard)
* Use these libraries to extract image features:
```
import cv2
from skimage.filters import prewitt_h,prewitt_v
```
* Image features that I'm planning to focus on:
  * horizontal and vertical edges detection (`skimage.filters.prewitt_h`, `skimage.filters.prewitt_v`)
  * converting colorspace (`cv2.cvtColor(img, cv2.COLOR_BGR2HSV)`) and extracting color features
  * etc.
* Use [Discogs Data Dump](https://discogs-data-dumps.s3.us-west-2.amazonaws.com/index.html) to get a list of music albums
* Based on the artist name and album name, try to find the album on Spotify and pair it with the list downloaded from Discogs
* Get covers for the given music albums
* Since the amout of favourites albums is not huge, I don't think it's a good idea to use a neural network. I found Cosine similarity most suitable for this type of problem

## Challenges

The challenge here is the extensive use of Spotify API, which I haven't try yet. At the same time, more computing resources will be needed to process the images and compare them with each other.

---
<img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/wasteland.png" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/lieben.jpg" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/the_raven_that_refused_to_sing.jpg" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/mezzanine.png" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/burn_to_grow.jpg" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/some_kind_of_piece.jpg" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/flying_colors.jpg" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/ok_computer.png" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/supernatural.jpg" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/on_an_island.jpg" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/polyphonic_prayer.jpg" width="125"> <img src="https://github.com/MrZH6/elements_of_AI_my_AI_idea/blob/main/album_covers/good_day.jpg" width="125">

---
